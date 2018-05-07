---
title: BLOB の取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 420e863fcd5d4c666bf8e9a25a2f0f53e726c871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="retrieving-a-blob"></a>BLOB の取得
さまざまな方法でバイナリ ラージ オブジェクト (BLOB) を取得することができます。 使用することができます**DBTYPE_BYTES**バイトのシーケンスとして BLOB を取得またはのようなインターフェイスを使用する`ISequentialStream`です。 詳細については、次を参照してください。 [BLOB と OLE オブジェクト](https://msdn.microsoft.com/en-us/library/ms711511.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 次のコードを使用して BLOB を取得する方法を示しています。`ISequentialStream`です。 マクロ[BLOB_ENTRY](../../data/oledb/blob-entry.md)インターフェイスとインターフェイスに使用するフラグを指定することができます。 コードを呼び出す、テーブルを開いたら、**読み取り**繰り返しで`ISequentialStream`BLOB からバイトを読み取ります。 コードの呼び出し**リリース**呼び出す前に、インターフェイス ポインターを破棄する`MoveNext`を次のレコードを取得します。  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories>> categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  

while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
 BLOB データを処理するマクロの詳細についてを参照してください「の列マップ マクロ」[用マクロおよびグローバル関数 OLE DB コンシューマー テンプレート](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)です。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)   
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)