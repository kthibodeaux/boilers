# boilers

1. Add `boiler` and `.boilers` (some basic examples) to your project directory.
2. Add the following to your vimrc: 
```
function BoilerBuilder()
  if filereadable("boiler") == 1
    if filereadable(@%) == 0
      read !./boiler %
      norm ggdd
    elseif line('$') == 1 && col('$') == 1
      read !./boiler %
      norm ggdd
    endif
  endif
endfunction

au BufNewFile,BufReadPost *.rb :call BoilerBuilder()
```
