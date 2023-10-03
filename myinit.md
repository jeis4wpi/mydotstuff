# Using scimax OSX with gnus

```lisp

(load "/usr/local/opt/scimax/share/emacs/site-lisp/scimax/init.el")

(require 'smart-tab)
(global-smart-tab-mode 1)

(defun kill-default-buffer ()
  "kill buffer withut prompt"
  (interactive)
  (let (kill-buffer-query-funtions) (kill-buffer))
  )

(global-set-key (kbd "C-x k") 'kill-default-buffer)
;;;(defalias 'yes-or-no-p 'y-or-n-p)

(setq mail-user-agent 'gnus-user-agent)
(require 'org-msg)
(setq org-msg-options "html-postamble:nil H:5 num:nil ^:{} toc:nil author:nil email:nil \\n:t"
      org-msg-startup "hidestars indent inlineimages"
      org-msg-greeting-fmt "\nHi%s,\n\n"
      org-msg-recipient-names '(("jpeismeier@wpi.edu" . "John"))
      org-msg-greeting-name-limit 3
      org-msg-default-alternatives '((new		. (text html))
				     (reply-to-html	. (text html))
				     (reply-to-text	. (text)))
      org-msg-convert-citation t
      org-msg-signature "

 Regards,

 #+begin_signature
 -- John
 #+end_signature")
(org-msg-mode)

```

