---
title: CMyProviderWindowsFile |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6f3badc08da7bd11e65c244c42c91ad37a584ca5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087267"
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile

ウィザードは、1 つの行のデータを格納するクラスを作成します。この場合、呼び出された`CMyProviderWindowsFile`します。 次のコードは`CMyProviderWindowsFile`ウィザードによって生成されたを使用してディレクトリ内のすべてのファイルを一覧表示され、`WIN32_FIND_DATA`構造体。 `CMyProviderWindowsFile` 継承、`WIN32_FIND_DATA`構造体。  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
   public WIN32_FIND_DATA  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
};  
```  
  
`CMyProviderWindowsFile` 呼び出されます、[ユーザー レコード クラス](../../data/oledb/user-record.md)プロバイダーの行セットの列を記述するマップも含まれています。 プロバイダーの列マップには、PROVIDER_COLUMN_ENTRY マクロを使用して行セット内の各フィールドの 1 つのエントリが含まれています。 マクロは、列の名前、序数に基づく、および構造体のエントリにオフセットを指定します。 上記のコードでプロバイダーの列のエントリにはオフセットが含まれて、`WIN32_FIND_DATA`構造体。 コンシューマーを呼び出すと`IRowset::GetData`、1 つの連続したバッファーでデータを転送します。 マップでは、ポインター演算を実行するよりも、データ メンバーを指定できます。  
  
`CMyProviderRowset`クラスも含まれています、`Execute`メソッド。 `Execute` 実際には、ネイティブなソースからのデータを読み取ります何ができます。 次のコードは、ウィザードで生成された`Execute`メソッド。 関数が使用する Win32`FindFirstFile`と`FindNextFile`、ディレクトリ内のファイルに関する情報を取得しのインスタンスに配置するための Api、`CMyProviderWindowsFile`クラス。  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
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
  
検索するディレクトリをによって表される`m_strCommandText`; によって表されるテキストが含まれます、`ICommandText`コマンド オブジェクトのインターフェイス。 ディレクトリが指定されていない場合は、現在のディレクトリが使用されます。  
  
メソッドは、ファイルが (1 行に対応) ごとに 1 つのエントリを作成しに格納、`m_rgRowData`データ メンバー。 `CRowsetImpl`クラスを定義、`m_rgRowData`データ メンバー。 この配列内のデータは、テーブル全体を表し、テンプレート全体で使用されます。  
  
## <a name="see-also"></a>関連項目  

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)