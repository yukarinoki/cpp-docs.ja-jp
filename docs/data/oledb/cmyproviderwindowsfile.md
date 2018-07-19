---
title: CMyProviderWindowsFile |Microsoft ドキュメント
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
ms.openlocfilehash: 8f0ba90bdcbaa4255757ee31015d0f6986862916
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097927"
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
ウィザードを 1 つの行のデータを格納するクラスを作成します。この場合、呼び出された`CMyProviderWindowsFile`です。 次のコードの`CMyProviderWindowsFile`生成ウィザードを使用して、ディレクトリ内のすべてのファイルを一覧表示、 **WIN32_FIND_DATA**構造体。 `CMyProviderWindowsFile` 継承、 **WIN32_FIND_DATA**構造体。  
  
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
  
 `CMyProviderWindowsFile` 呼び出された、[ユーザー レコード クラス](../../data/oledb/user-record.md)プロバイダーの行セットの列を記述するマップも含まれているためです。 プロバイダーの列マップには、PROVIDER_COLUMN_ENTRY マクロを使用して行セットのフィールドごとに 1 つのエントリが含まれています。 マクロは、列名、序数に基づく、および構造エントリへのオフセットを指定します。 上記のコードでプロバイダーの列のエントリにオフセットが含まれて、 **WIN32_FIND_DATA**構造体。 コンシューマーを呼び出すと**irowset::getdata**、1 つの連続するバッファーでデータを転送します。 を行うには、ポインターの算術演算を行うのではなく、マップにデータ メンバーを指定することができます。  
  
 `CMyProviderRowset`クラスも含まれています、`Execute`メソッドです。 `Execute` どのような実際にデータを読み取り、ネイティブのソースからです。 次のコードは、ウィザードで生成された`Execute`メソッドです。 関数は、Win32 を使用して**FindFirstFile**と`FindNextFile`ディレクトリ内のファイルに関する情報を取得しのインスタンスに配置するための Api、`CMyProviderWindowsFile`クラスです。  
  
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
  
 検索するディレクトリがによって表される`m_strCommandText`; によって表されるテキストを含むこの、`ICommandText`コマンド オブジェクトのインターフェイスです。 ディレクトリが指定されていない場合は、現在のディレクトリが使用されます。  
  
 このメソッドは、(1 行に対応) の各ファイルの 1 つのエントリを作成しに格納、 **m_rgRowData**データ メンバーです。 `CRowsetImpl`クラスを定義、 **m_rgRowData**データ メンバーです。 この配列内のデータは、テーブル全体を表し、すべてのテンプレートで使用されます。  
  
## <a name="see-also"></a>関連項目  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)