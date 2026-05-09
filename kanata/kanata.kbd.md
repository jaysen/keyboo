;; ============================================================
;; kanata.kbd  —  key60 universal nav layer
;;
;; CapsLock:  tap → Escape  |  hold → nav layer
;;
;; NAV LAYER REFERENCE
;; ─────────────────────────────────────────────────────────
;; Function keys
;;   1 2 3 4 5 6 7 8 9 0 - =  →  F1–F12
;;
;; Delete / Backspace (left hand top)
;;   Tab → Backspace          Q → Delete (fwd)
;;
;; Arrows — left hand
;;   W / E → Up               A → Left
;;   S → Down                 D → Right
;;
;; Select up/down (left hand)
;;   R → Shift+Up             F → Shift+Down
;;   T → Shift+PgUp           G → Shift+PgDn
;;
;; Arrows — right hand (IJKL)
;;   I → Up    J → Left    K → Down    L → Right
;;
;; Word jump (right hand home row)
;;   H → Ctrl+Left            ; / ' → Ctrl+Right
;;
;; Line Home/End (right hand top row)
;;   U → Home                 O → End
;;
;; Select to line start/end (right hand top row)
;;   Y → Shift+Home           P → Shift+End
;;
;; Select to line start/end (left hand bottom)
;;   Z → Shift+Home           X → Shift+End
;;
;; Select by char/word (right hand bottom)
;;   N → Shift+Ctrl+Left      M → Shift+Left
;;   . → Shift+Right          / → Shift+Ctrl+Right
;;
;; tap-hold: 200ms — reduce to 150ms once muscle memory is solid
;; ============================================================


(defsrc
  caps
  1    2    3    4    5    6    7    8    9    0    -    =
  tab  q    w    e    r    t    y    u    i    o    p
  a    s    d    f    g    h    j    k    l    ;    '
  z    x    c    v    b    n    m    ,    .    /
)


(deflayer base
  (tap-hold 200 200 esc (layer-while-held nav))
  _    _    _    _    _    _    _    _    _    _    _    _
  _    _    _    _    _    _    _    _    _    _    _
  _    _    _    _    _    _    _    _    _    _    _
  _    _    _    _    _    _    _    _    _    _
)


(deflayer nav
  ;;   caps
       _
  ;;   1     2     3     4     5     6     7     8     9     10    -     =
       f1    f2    f3    f4    f5    f6    f7    f8    f9    f10   f11   f12
  ;;   tab   q     w     e     r     t     y     u     i     o     p
       bspc  del   up    up    S-up  S-pgup S-home home  up    end   S-end
  ;;   a     s     d     f     g     h      j     k     l     ;      '
       left  down  rght  S-down S-pgdn C-left left  down  rght  C-rght C-rght
  ;;   z      x      c    v    b    n        m      ,    .      /
       S-home S-end  _    _    _    S-C-left S-left _    S-rght S-C-rght
)


(defalias
  nav (layer-while-held nav)
)