# HOW TO FIX ERROR INSTALL VENV EMOI 
## Eror "failed to `make -j4`" - Failed to install CPython-3.7.4. Check /Users/traitran/.pythonz/log/build.log to see why.
1. Install "pyenv"
    brew install pyenv 
2. 
    pyenv install 3.6.9
3. 
    pyenv install --patch 3.6.9 < <(curl -sSL https://github.com/python/cpython/commit/8ea6353.patch\?full_index\=1)
4. 
    mv 3.6.9 CPython-3.6.9 