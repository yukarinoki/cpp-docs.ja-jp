---
title: OLE DB プロバイダーへの文字列の読み取り |Microsoft Docs
ms.custom: ''
ms.date: 10/13/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b51611ff5727a89e47bef569865f915a189a993
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410658"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>OLE DB プロバイダーへの文字列の読み込み

`RMyProviderRowset::Execute`関数は、ファイルを開くし、文字列を読み取る。 呼び出して、コンシューマーがプロバイダーにファイル名を渡します[icommandtext::setcommandtext](/previous-versions/windows/desktop/ms709757)します。 プロバイダーは、ファイル名を受け取るし、メンバー変数に格納`m_szCommandText`します。 `Execute` ファイル名を読み取って`m_szCommandText`します。 ファイル名が無効か、ファイルが使用できない場合`Execute`エラーが返されます。 ファイルと呼び出しを開き、それ以外の場合、`fgets`文字列を取得します。 各セットの文字列の読み取り、`Execute`ユーザー レコードのインスタンスを作成します (`CAgentMan`) と配列に配置します。  
  
ファイルを開けない場合`Execute`DB_E_NOTABLE を返す必要があります。 E_FAIL を代わりに返された場合、プロバイダーが多数のコンシューマーでは動作せず、OLE DB に合格しない[準拠合致テスト](../../data/oledb/testing-your-provider.md)します。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  

編集、`Execute`関数に次のようになります。  
  
### <a name="code"></a>コード  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
class RMyProviderRowset : public CRowsetImpl< RMyProviderRowset, CAgentMan, CRMyProviderCommand>  
{  
public:  
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
    {  
        enum {  
            sizeOfBuffer = 256,  
            sizeOfFile = MAX_PATH  
        };  
        USES_CONVERSION;  
        FILE* pFile = NULL;  
        TCHAR szString[sizeOfBuffer];  
        TCHAR szFile[sizeOfFile];  
        size_t nLength;        errcodeerr;  
  
        ObjectLock lock(this);  
  
        // From a filename, passed in as a command text, scan the file  
        // placing data in the data array.  
        if (!m_szCommandText)  
        {  
            ATLTRACE("No filename specified");  
            return E_FAIL;  
        }  
  
        // Open the file  
        _tcscpy_s(szFile, sizeOfFile, m_szCommandText);  
        if (szFile[0] == _T('\0') ||   
            ((err = fopen_s(&pFile, &szFile[0], "r")) == 0))  
        {  
            ATLTRACE("Could not open file");  
            return DB_E_NOTABLE;  
        }  
  
        // Scan and parse the file.  
        // The file should contain two strings per record  
        LONG cFiles = 0;  
        while (fgets(szString, sizeOfBuffer, pFile) != NULL)  
        {  
            nLength = strnlen(szString, sizeOfBuffer);  
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF  
            CAgentMan am;  
            _tcscpy_s(am.szCommand, am.sizeOfCommand, szString);  
            _tcscpy_s(am.szCommand2, am.sizeOfCommand2, szString);  
  
            if (fgets(szString, sizeOfBuffer, pFile) != NULL)  
            {  
                nLength = strnlen(szString, sizeOfBuffer);  
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF  
                _tcscpy_s(am.szText, am.sizeOfText, szString);  
                _tcscpy_s(am.szText2, am.sizeOfText2, szString);  
            }  
  
            am.dwBookmark = ++cFiles;  
            if (!m_rgRowData.Add(am))  
            {  
                ATLTRACE("Couldn't add data to array");  
                fclose(pFile);  
                return E_FAIL;  
            }  
        }  
  
        if (pcRowsAffected != NULL)  
            *pcRowsAffected = cFiles;  
        return S_OK;  
    }  
}  
```  
  
## <a name="see-also"></a>関連項目  

[単純な読み取り専用プロバイダーの実装](../../data/oledb/implementing-the-simple-read-only-provider.md)