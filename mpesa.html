<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M-Pesa Payment</title>
    <style>
        .mpesa-form-container {
            max-width: 500px;
            margin: 20px auto;
            padding: 20px;
            background: #ffffff;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }

        .mpesa-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .mpesa-header img {
            max-width: 200px;
            margin-bottom: 15px;
        }

        .mpesa-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .form-group label {
            font-weight: 500;
            color: #333;
        }

        .form-group input {
            padding: 12px;
            border: 2px solid #e1e1e1;
            border-radius: 6px;
            font-size: 16px;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus {
            outline: none;
            border-color: #4CAF50;
        }

        .error {
            color: #dc3545;
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }

        .pay-button {
            background: #4CAF50;
            color: white;
            padding: 14px;
            border: none;
            border-radius: 6px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .pay-button:hover {
            background: #45a049;
        }

        .pay-button:disabled {
            background: #cccccc;
            cursor: not-allowed;
        }

        .loading-spinner {
            display: none;
            width: 20px;
            height: 20px;
            margin: 0 auto;
            border: 3px solid #f3f3f3;
            border-top: 3px solid #4CAF50;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .status-message {
            text-align: center;
            margin-top: 20px;
            padding: 10px;
            border-radius: 6px;
            display: none;
        }

        .status-success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }

        .status-error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }

        @media (max-width: 600px) {
            .mpesa-form-container {
                margin: 10px;
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="mpesa-form-container">
        <div class="mpesa-header">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/15/M-PESA_LOGO-01.png/320px-M-PESA_LOGO-01.png" alt="M-Pesa Logo">
            <h2>Make Payment</h2>
        </div>

        <form id="mpesaPaymentForm" class="mpesa-form">
            <div class="form-group">
                <label for="phone">Phone Number</label>
                <input type="tel" id="phone" name="phone" placeholder="e.g., 0726057525" required>
                <span class="error" id="phoneError">Please enter a valid Safaricom number</span>
            </div>

            <div class="form-group">
                <label for="amount">Amount (KES)</label>
                <input type="number" id="amount" name="amount" min="1" step="1" placeholder="Enter amount" required>
                <span class="error" id="amountError">Please enter a valid amount</span>
            </div>

            <button type="submit" class="pay-button" id="payButton">
                Pay with M-Pesa
            </button>

            <div class="loading-spinner" id="loadingSpinner"></div>
            <div class="status-message" id="statusMessage"></div>
        </form>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const form = document.getElementById('mpesaPaymentForm');
            const phoneInput = document.getElementById('phone');
            const amountInput = document.getElementById('amount');
            const payButton = document.getElementById('payButton');
            const loadingSpinner = document.getElementById('loadingSpinner');
            const statusMessage = document.getElementById('statusMessage');
            const phoneError = document.getElementById('phoneError');
            const amountError = document.getElementById('amountError');

            // Format phone number as user types
            phoneInput.addEventListener('input', function(e) {
                let phone = e.target.value.replace(/\D/g, '');
                if (phone.startsWith('0')) {
                    phone = '254' + phone.substring(1);
                } else if (phone.startsWith('7') || phone.startsWith('1')) {
                    phone = '254' + phone;
                }
                validatePhone(phone);
            });

            // Validate amount as user types
            amountInput.addEventListener('input', function(e) {
                validateAmount(e.target.value);
            });

            function validatePhone(phone) {
                const phoneRegex = /^254[7,1]\d{8}$/;
                const isValid = phoneRegex.test(phone);
                phoneError.style.display = isValid ? 'none' : 'block';
                return isValid;
            }

            function validateAmount(amount) {
                const isValid = amount > 0;
                amountError.style.display = isValid ? 'none' : 'block';
                return isValid;
            }

            function showMessage(message, isError = false) {
                statusMessage.textContent = message;
                statusMessage.style.display = 'block';
                statusMessage.className = 'status-message ' + 
                    (isError ? 'status-error' : 'status-success');
            }

            function setLoading(loading) {
                payButton.disabled = loading;
                loadingSpinner.style.display = loading ? 'block' : 'none';
                payButton.textContent = loading ? 'Processing...' : 'Pay with M-Pesa';
            }

            form.addEventListener('submit', async function(e) {
                e.preventDefault();

                const phone = phoneInput.value.trim();
                const amount = parseFloat(amountInput.value);

                if (!validatePhone(phone) || !validateAmount(amount)) {
                    return;
                }

                setLoading(true);
                statusMessage.style.display = 'none';

                try {
                    // Replace this URL with your WordPress ajax endpoint
                    const response = await fetch(ajaxurl, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/x-www-form-urlencoded',
                        },
                        body: new URLSearchParams({
                            action: 'process_mpesa_payment',
                            phone: phone,
                            amount: amount
                        })
                    });

                    const data = await response.json();

                    if (data.success) {
                        showMessage('STK Push sent successfully. Please check your phone to complete the payment.');
                        form.reset();
                    } else {
                        showMessage(data.error || 'Failed to initiate payment. Please try again.', true);
                    }
                } catch (error) {
                    showMessage('An error occurred. Please try again later.', true);
                } finally {
                    setLoading(false);
                }
            });
        });
    </script>
</div>
</body>
</html>
