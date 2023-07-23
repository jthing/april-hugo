---
title: "GLSL"
date: 2023-07-23T00:00:00+02:00
draft: false
---

## GLSL interface {#glsl-interface}

[GLSL at github](<https://github.com/KhronosGroup/glslang>)
First clone this locally. &lt;root&gt;/Test contains example GLSL scripts./

The files here use CRLF windows style line endings to fix include

```emacs-lisp
(use-package glsl-mode)

(defun jpt/cr-sanitise ()
  "Make sure current buffer uses unix-utf8 encoding.
If necessary remove superfluous ^M. Buffer will need to be saved
for changes to be permanent."
  (interactive)
  (set-buffer-file-coding-system 'utf-8-unix)
  (delete-trailing-whitespace)
  (message "Please save buffer to persist encoding changes."))

(defun jpt/rm-cr ()
  "Remove ^M at end of line in the whole buffer."
  (interactive)
  (save-match-data
    (save-excursion
      (let ((remove-count 0))
        (goto-char (point-min))
        (while (re-search-forward (concat (char-to-string 13) "$") (point-max) t)
          (setq remove-count (+ remove-count 1))
          (replace-match "" nil nil))
        (message (format "%d ^M removed from buffer." remove-count))))))

```

-   compile glsl for vulcan glslc --target-spv=spv1.3 spv.1.3.coopmat.comp -o spv.1.3.coopmat.spv
-   disassemble bytecode to spir-v: spirv-dis spv.1.3.coopmat.spv

These utilities are available from [google shaderc at github](<https://github.com/google/shaderc>)
