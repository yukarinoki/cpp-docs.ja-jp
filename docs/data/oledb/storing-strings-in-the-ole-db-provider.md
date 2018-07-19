---
title: OLE DB プロバイダーで文字列を格納する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5ba289e7e53ba1bcaca550ba84c2d871d215306
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106987"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>OLE DB プロバイダーへの文字列の格納
ATL OLE DB プロバイダー ウィザードと呼ばれる既定のユーザー レコードの作成 myproviderrs.h、`CWindowsFile`です。 変更するか、2 つの文字列を処理する`CWindowsFile`または次のコードに示すように、ユーザー レコードを追加します。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 データ メンバー`szCommand`と`szText`で 2 つの文字列を表す`szCommand2`と`szText2`必要な場合は、追加の列を提供します。 データ メンバー`dwBookmark`この単純な読み取り専用プロバイダーは必要ありませんが、後で追加するため、`IRowsetLocate`インターフェイス; を参照してください[、単純な読み取り専用プロバイダーの向上](../../data/oledb/enhancing-the-simple-read-only-provider.md)です。 `==`インスタンスを比較演算子 (この演算子の実装は省略可能)。  
  
 これは、プロバイダーはコンパイルして実行する準備ができます。 プロバイダーをテストするには、照合機能を持つコンシューマー必要があります。 [単純なコンシューマーを実装する](../../data/oledb/implementing-a-simple-consumer.md)このようなテスト コンシューマーを作成する方法を示します。 プロバイダーをテスト コンシューマーを実行します。 クリックすると、テストのコンシューマーが、プロバイダーから適切な文字列を取得することを確認、**実行**ボタンをクリックして、**テスト コンシューマー**  ダイアログ ボックス。  
  
 プロバイダーを正常にテストするときに、追加のインターフェイスを実装することでその機能を強化することができます。 例が示すように[単純な読み取り専用プロバイダーの向上](../../data/oledb/enhancing-the-simple-read-only-provider.md)です。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの実装](../../data/oledb/implementing-the-simple-read-only-provider.md)