A simple script for sending messages to kestrel. this is working like tail commands. stdin also support! ;)

# Usage

    $ kestrel_tail --queue your_queue_name --host_ports kestrel_hosts1:22133 kestrel_hosts2:22133 --rewind true --num_threads 10 -lv DEBUG your_file_name

    $ kestrel_tail --help
    usage: kestrel_tail [-h] [-v] -q QUEUE [-n NUM_THREADS]
                        [-l [HOST_PORTS [HOST_PORTS ...]]] [--rewind REWIND]
                        [--follow_delay FOLLOW_DELAY]
                        [--read_line_buf_size READ_LINE_BUF_SIZE]
                        [--flush_interval FLUSH_INTERVAL]
                        [--fail_store_path FAIL_STORE_PATH]
                        [--fail_store_log_rotate_when {S,M,H,D,W,midnight}]
                        [--fail_store_log_rotate_rollover_interval FAIL_STORE_LOG_ROTATE_ROLLOVER_INTERVAL]
                        [--fail_store_backup_count FAIL_STORE_BACKUP_COUNT]
                        [-lv LOG_LEVEL] [-lp LOG_FILE_PATH]
                        [FILE]

    Follow file and send data to kestrel.

    positional arguments:
      FILE                  File to follow. if not given, use stdin.

    optional arguments:
      -h, --help            show this help message and exit
      -v, --version         show program's version number and exit
      -q QUEUE, --queue QUEUE
                            queue name
      -n NUM_THREADS, --num_threads NUM_THREADS
                            number of worker threads
      -l [HOST_PORTS [HOST_PORTS ...]], --host_ports [HOST_PORTS [HOST_PORTS ...]]
                            ketrel host:port pairs (default: 127.0.0.1:22113)ex)
                            -l myhost1:port myhost2:port
      --rewind REWIND       start read the file from the beginning (default:
                            false)
      --follow_delay FOLLOW_DELAY
                            follow file delay(Sec) (default: 0.5)
      --read_line_buf_size READ_LINE_BUF_SIZE
                            read line buffer size (default: 0)
      --flush_interval FLUSH_INTERVAL
                            flush read line buffer interval(Sec) (default: 0.0)
      --fail_store_path FAIL_STORE_PATH
                            store path to write kestrel send failed data (default:
                            same with FILE's directory)
      --fail_store_log_rotate_when {S,M,H,D,W,midnight}
                            fail store log rotate when depending on the rollover
                            interval (default: H). for more information, visit htt
                            p://docs.python.org/library/logging.handlers.html#time
                            drotatingfilehandler
      --fail_store_log_rotate_rollover_interval FAIL_STORE_LOG_ROTATE_ROLLOVER_INTERVAL
                            fail store log rotate rollover interval(default: 1)
      --fail_store_backup_count FAIL_STORE_BACKUP_COUNT
                            fail store file backup count (default: 5)
      -lv LOG_LEVEL, --log_level LOG_LEVEL
                            logging level(default: ERROR)
      -lp LOG_FILE_PATH, --log_file_path LOG_FILE_PATH
                            log file path. if not given, stderr will be used.

