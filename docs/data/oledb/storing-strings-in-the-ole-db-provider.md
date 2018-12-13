---
title: OLE DB プロバイダーへの文字列の格納
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 54dfdb347c621cf6f8645feb6d13742f32503f9f
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264620"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>OLE DB プロバイダーへの文字列の格納

*カスタム*RS.h、 **ATL OLE DB プロバイダー ウィザード**と呼ばれる既定のユーザー レコードを作成します。`CWindowsFile`します。 2 つの文字列を処理するために次のように変更します。`CWindowsFile`次のコードに示すようにします。

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

データ メンバー`szCommand`と`szText`で 2 つの文字列を表す`szCommand2`と`szText2`必要な場合、追加の列とします。 データ メンバー`dwBookmark`この単純な読み取り専用プロバイダーは必要ありませんが、後で追加に使用されます、`IRowsetLocate`インターフェイスは、参照してください[、単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md)します。 `==`演算子とインスタンスを比較します (この演算子の実装は省略可能)。

機能を追加するにはこれが完了したら、 [OLE DB プロバイダーへの文字列の読み取り](../../data/oledb/reading-strings-into-the-ole-db-provider.md)します。

## <a name="see-also"></a>関連項目

[単純な読み取り専用プロバイダーの実装](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
