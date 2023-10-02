# my gnus el file so far

```lisp

;;;https://www.emacswiki.org/emacs/GnusSpeed
(setq gc-cons-threshold 3500000)
(setq gnus-use-correct-string-widths nil)

(setq user-full-name '"John Eismeier")
(setq user-mail-address '"jpeismeier@wpi.edu")

(setq message-send-mail-function 'smtpmail-send-it
    smtpmail-default-smtp-server "localhost"
    smtpmail-smtp-server "localhost"
    user-mail-address "jpeismeier@wpi.edu"
    smtpmail-smtp-service 5003
    )

(setq nnmail-expiry-target "nnimap:expired")

(setq gnus-select-method
                '(nnimap "localhost"
                          (nnimap-address "localhost")
                          (nnimap-server-port 5001)
                          (nnimap-expunge t)
                          (nnir-search-engine imap)
                          (nnmail-expiry-wait 30)
                          (nnimap-stream network)))

(setq gnus-posting-styles
  '((".*" ; Matches all groups of messages
    (address "John Eismeier <jpeismeier@wpi.edu>")
    (From "John Eismeier <jpeismeier@wpi.edu>")
    ("X-Message-SMTP-Method" "smtp localhost 5003 jpeismeier@wpi.edu"))))

```

# what will speed up this approach?

# Reference:

[languages](https://github.com/github-linguist/linguist/blob/master/lib/linguist/languages.yml#L743)
