async uploadMedia(phoneNumberId, accessToken, fileBuffer, fileName, contentType) {
        try {
            logger.info(`Iniciando upload do arquivo: ${fileName}`, 'UPLOAD');
            const formData = new FormData();
            formData.append('messaging_product', 'whatsapp');
            formData.append('file', fileBuffer, {
                filename: fileName,
                contentType: contentType
            });

            const uploadRes = await this.withRetry(() =>
                axios.post(
                    `https://graph.facebook.com/v19.0/${phoneNumberId}/media`,
                    formData,
                    {
                        headers: {
                            'Authorization': `Bearer ${accessToken}`,
                            ...formData.getHeaders()
                        }
                    }
                )
            );
            logger.success(`Upload concluído. Media ID: ${uploadRes.data.id}`, 'UPLOAD');
            return uploadRes.data.id;
        } catch (error) {
            const errorDetails = {
                message: error.message,
                status: error.response?.status,
                statusText: error.response?.statusText,
                data: error.response?.data,
                fileName: fileName,
                stack: error.stack
            };
            logger.error(`Erro no upload: ${JSON.stringify(errorDetails, null, 2)}`, 'UPLOAD');
            throw error;
        }
    }




    async sendDocument(phoneNumberId, accessToken, targetNumber, mediaId, fileName) {
        try {
            logger.info(`Enviando documento ${fileName} para ${targetNumber}`, 'SEND_DOC');
            await this.withRetry(() =>
                axios.post(
                    `https://graph.facebook.com/v19.0/${phoneNumberId}/messages`,
                    {
                        messaging_product: 'whatsapp',
                        to: targetNumber,
                        type: 'document',
                        document: { id: mediaId, filename: fileName }
                    },
                    { headers: { 'Authorization': `Bearer ${accessToken}`, 'Content-Type': 'application/json' } }
                )
            );
            logger.success(`Documento ${fileName} enviado com sucesso!`, 'SEND_DOC');
        } catch (error) {
            const errorDetails = {
                message: error.message,
                status: error.response?.status,
                statusText: error.response?.statusText,
                data: error.response?.data,
                fileName: fileName,
                targetNumber: targetNumber,
                mediaId: mediaId,
                stack: error.stack
            };
            logger.error(`Erro ao enviar documento: ${JSON.stringify(errorDetails, null, 2)}`, 'SEND_DOC');
            throw error;
        }


        
    }
