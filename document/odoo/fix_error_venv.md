# HOW TO FIX ERROR INSTALL VENV EMOI 
## Eror "failed to `make -j4`" - Failed to install CPython-3.7.4. Check /Users/traitran/.pythonz/log/build.log to see why.
1. Install "pyenv", khởi tạo môi trường python

    brew install pyenv 

2. Install python 3.6.9 trong môi trường pyenv

    pyenv install 3.6.9

3. Nếu bị lỗi, thực hiện vá bản lỗi bằng patch

    pyenv install --patch 3.6.9 < <(curl -sSL https://github.com/python/cpython/commit/8ea6353.patch\?full_index\=1)
    
4. Move python 3.6.9 into CPython-3.6.9

    mv 3.6.9 CPython-3.6.9 
5. How to check version pythonz

    ls ~/.pythonz/pythons

6. Sau khi cài đặt xong python 3.6.9, copy python 3.6.9 sang pythonz

    cp -r /Users/traitran/.pyenv/versions/3.6.9 ~/.pythonz/pythons/

7. Copy python 3.6.9 sang CPython-3.6.9

    mv 3.6.9 CPython-3.6.9 

8. Kiểm tra list python

    pew list_pythons