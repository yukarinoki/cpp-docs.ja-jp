---
description: CCustomWindowsFile の詳細情報
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
ms.openlocfilehash: c0df2840b68a350f9d65102fdf0a962681edefd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170400"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

ウィザードによって、1行のデータを含むクラスが作成されます。この場合は、と呼ばれ `CCustomWindowsFile` ます。 の次のコード `CCustomWindowsFile` は、ウィザードで生成され、構造体を使用してディレクトリ内のすべてのファイルを一覧表示し `WIN32_FIND_DATA` ます。 `CCustomWindowsFile` 構造体から継承し `WIN32_FIND_DATA` ます。

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

`CCustomWindowsFile` は、プロバイダーの行セット内の列を説明するマップも持っているため、 [ユーザーレコードクラス](../../data/oledb/user-record.md) と呼ばれます。 プロバイダー列マップには、PROVIDER_COLUMN_ENTRY マクロを使用して、行セットの各フィールドに1つのエントリが含まれています。 マクロは、列名、序数、および構造エントリへのオフセットを指定します。 上のコードのプロバイダー列エントリには、構造体へのオフセットが含まれて `WIN32_FIND_DATA` います。 コンシューマーがを呼び出すと `IRowset::GetData` 、データは1つの連続するバッファーで転送されます。 このマップでは、ポインター演算を実行するのではなく、データメンバーを指定することができます。

クラスには `CCustomRowset` 、メソッドも含まれてい `Execute` ます。 `Execute` は、実際にはネイティブソースからのデータを読み取るものです。 次のコードは、ウィザードで生成されたメソッドを示して `Execute` います。 関数は、Win32 と api を使用して `FindFirstFile` `FindNextFile` ディレクトリ内のファイルに関する情報を取得し、クラスのインスタンスに配置し `CCustomWindowsFile` ます。

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

検索するディレクトリはによって示されます。これには、 `m_strCommandText` コマンドオブジェクトのインターフェイスによって表されるテキストが含まれ `ICommandText` ます。 ディレクトリが指定されていない場合は、現在のディレクトリが使用されます。

メソッドは、(行に対応する) 各ファイルに対して1つのエントリを作成し、データメンバーに格納し `m_rgRowData` ます。 クラスは、 `CRowsetImpl` データメンバーを定義し `m_rgRowData` ます。 この配列内のデータはテーブル全体に表示され、テンプレート全体で使用されます。

## <a name="see-also"></a>関連項目

[プロバイダー Wizard-Generated ファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
