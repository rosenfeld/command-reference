# Measuring requests timing with Curl

    curl -I url -w %{time_connect}:%{time_starttransfer}:%{time_total}\\n

Headers can be passed with -H and you can get all your cookies for authenticated requests by
right-clicking the request in the Chrome's developer's tool and choosing Copy as cURL. Just
append -I (or -o /dev/null if you're not interested in the header) and the options above.
