# qr
// Import the necessary library
const QRCode = require('qrcode');

/**
 * Generates a QR code for the given data.
 * 
 * @param {string} data - The data to be encoded in the QR code.
 * @returns {Promise<string>} - A promise that resolves with the QR code as a data URL.
 */
function generateQRCode(data) {
  return new Promise((resolve, reject) => {
    try {
      // Generate the QR code
      QRCode.toDataURL(data, (err, url) => {
        if (err) {
          reject(err);
        } else {
          resolve(url);
        }
      });
    } catch (error) {
      // Log any errors
      console.error(error);
      reject(error);
    }
  });
}
