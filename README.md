## Requirements

**1. Download & install Addons for IIS10 Web Server.**

   - [httpplatformhandlermodule_x64_en_v2_9.0.5.msi](https://docs.lextudio.com/blog/httpplatformhandler-v2/)
   - [requestRouter_amd64.msi](https://download.microsoft.com/download/e/9/8/e9849d6a-020e-47e4-9fd0-a023e99b54eb/requestRouter_amd64.msi)
   - [rewrite_amd64_en-US.msi](https://download.microsoft.com/download/1/2/8/128E2E22-C1B9-44A4-BE2A-5859ED1D4592/rewrite_amd64_en-US.msi)

**2. Turn Windows Features on or off**
  - .NET Framework 3.5
  - .NET Framework 4.8 Advanced Services
  - Internet Information Services
    - World Wide Web Services
       - Application Development Features (Select All)    
       - Common HTTP Features (Select All)
       - Health and Diagnostics (Select All)
       - Performance Features (Select All)
       - Security (Select All)
  - Internet Information Services Hostable Web Core
    
**3. Create an Streamlit Application (UV and python Virtual Environment).**
    
    - **Note:** Order is required otherwise `(StreamLitApp)` won't be seen rather than `(venv)` in the console.
    
    ```ps
    PS C:\Users\username>mkdir StreamLitApp && cd StreamLitApp
    PS C:\Users\username\StreamLitApp>uv init --python 3.11.2
    Initialized project `StreamLitApp`
    PS C:\Users\username\StreamLitApp>uv venv --python 3.11.2
    Using CPython 3.11.2 interpreter at: C:\Python311\python.exe
    Creating virtual environment at: .venv
    Activate with: .venv\Scripts\activate
    PS C:\Users\username>\StreamLitApp>.venv\Scripts\activate
    (StreamLitApp) PS C:\Users\username\StreamLitApp> uv add streamlit plotly plotly-express lxml openpyxl pyyml toml
    ```
    
**4. Basic Streamlit Application Template**

   1. Add this to the `main.py`
      
   ```py
   import streamlit as st
   
   def set_page_config():
    st.set_page_config(
        page_title="Sales Dashboard",
        page_icon=":bar_chart:",
        layout="wide",
        initial_sidebar_state="expanded",
    )
    st.markdown("<style> footer {visibility: hidden;} </style>", unsafe_allow_html=True)
   
   def main():
    set_page_config()

   if __name__ == "__main__":
    main()
   ```

   2. Run the App from command line
      
   ```PS
    PS C:\Users\username>\StreamLitApp>streamlit run main.py
      You can now view your Streamlit app in your browser.

      Local URL: http://localhost:8501
      Network URL: http://<ip-address>:8501
   ```   
   
