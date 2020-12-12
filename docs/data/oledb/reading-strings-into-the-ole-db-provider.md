---
description: 詳細については、「OLE DB プロバイダーへの文字列の読み取り」を参照してください。
title: OLE DB プロバイダーへの文字列の読み込み
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: 5df8812d5589dd457684bf5e36a8a49f798f99aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286632"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>OLE DB プロバイダーへの文字列の読み込み

関数は、 `CCustomRowset::Execute` ファイルを開き、文字列を読み取ります。 コンシューマーは、 [ICommandText:: SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85))を呼び出すことによって、ファイル名をプロバイダーに渡します。 プロバイダーはファイル名を受け取り、それをメンバー変数に格納し `m_strCommandText` ます。 `Execute` ファイル名をから読み取り `m_strCommandText` ます。 ファイル名が無効な場合、またはファイルが使用できない場合は、 `Execute` エラーが返されます。 それ以外の場合は、ファイルを開き、を呼び出して `fgets` 文字列を取得します。 が読み取る文字列のセットごとに、 `Execute` ( `CCustomWindowsFile` [OLE DB プロバイダーに文字列を格納](../../data/oledb/storing-strings-in-the-ole-db-provider.md)することによって変更された) ユーザーレコードのインスタンスを作成し、配列に格納します。

ファイルを開くことができない場合、は `Execute` DB_E_NOTABLE を返す必要があります。 代わりに E_FAIL が返された場合、プロバイダーは多くのコンシューマーで動作せず、OLE DB [準拠テスト](../../data/oledb/testing-your-provider.md)に合格しません。

## <a name="example"></a>例

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
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
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
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
};
```

この処理が完了すると、プロバイダーはコンパイルして実行できる状態になります。 プロバイダーをテストするには、対応する機能を持つコンシューマーが必要です。 [単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md) は、このようなテストコンシューマーを作成する方法を示しています。 プロバイダーを使用してテストコンシューマーを実行し、テストコンシューマーがプロバイダーから適切な文字列を取得することを確認します。

プロバイダーのテストが正常に完了したら、追加のインターフェイスを実装して機能を強化することができます。 例については [、「Simple Read-Only Provider の強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)」を参照してください。

## <a name="see-also"></a>関連項目

[単純な Read-Only プロバイダーの実装](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
