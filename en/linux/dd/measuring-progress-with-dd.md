# Measuring progress with dd

As root:

    dd if=/dev/zero of=/dev/null & pid=$! ; watch -n 3 kill -USR1 $pid
