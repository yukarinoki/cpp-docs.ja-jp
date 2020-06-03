---
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: 103a1ce5568c6137994056e574ce8eec04511d8f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079741"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

ウィザードによって、1行のデータを含むクラスが作成されます。この場合、`CCustomWindowsFile`と呼ばれます。 次の `CCustomWindowsFile` のコードはウィザードで生成され、`WIN32_FIND_DATA` 構造を使用してディレクトリ内のすべてのファイルを一覧表示します。 `CCustomWindowsFile` は `WIN32_FIND_DATA` 構造から継承されます。

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` は、プロバイダーの行セット内の列を説明するマップも持っているため、[ユーザーレコードクラス](../../data/oledb/user-record.md)と呼ばれます。 プロバイダー列マップには、PROVIDER_COLUMN_ENTRY マクロを使用して、行セットの各フィールドに1つのエントリが含まれています。 マクロは、列名、序数、および構造エントリへのオフセットを指定します。 上のコードのプロバイダー列エントリには、`WIN32_FIND_DATA` 構造体へのオフセットが含まれています。 コンシューマーが `IRowset::GetData`を呼び出すと、データは1つの連続するバッファーで転送されます。 このマップでは、ポインター演算を実行するのではなく、データメンバーを指定することができます。

`CCustomRowset` クラスには、`Execute` メソッドも含まれています。 `Execute` は、実際にはネイティブソースからのデータを読み取ります。 次のコードは、ウィザードで生成された `Execute` メソッドを示しています。 関数は、Win32 の `FindFirstFile` Api と `FindNextFile` Api を使用してディレクトリ内のファイルに関する情報を取得し、`CCustomWindowsFile` クラスのインスタンスに配置します。

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

検索するディレクトリは `m_strCommandText`によって表示されます。これには、command オブジェクトの `ICommandText` インターフェイスによって表されるテキストが含まれます。 ディレクトリが指定されていない場合は、現在のディレクトリが使用されます。

メソッドは、(行に対応する) 各ファイルに対して1つのエントリを作成し、`m_rgRowData` データメンバーに格納します。 `CRowsetImpl` クラスは、`m_rgRowData` データメンバーを定義します。 この配列内のデータはテーブル全体に表示され、テンプレート全体で使用されます。

## <a name="see-also"></a>参照

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
