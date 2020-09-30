---
title: BLOB の取得
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: 352841595e8b197407ccb52a22c8b0502d314c98
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509503"
---
# <a name="retrieving-a-blob"></a>BLOB の取得

バイナリラージオブジェクト (BLOB) は、さまざまな方法で取得できます。 を使用すると、 `DBTYPE_BYTES` BLOB をバイトシーケンスとして取得したり、のようなインターフェイスを使用したりでき `ISequentialStream` ます。 詳細については、 **OLE DB プログラマーリファレンス**の「 [Blob と OLE オブジェクト](/previous-versions/windows/desktop/ms711511(v=vs.85))」を参照してください。

次のコードは、を使用して BLOB を取得する方法を示して `ISequentialStream` います。 マクロ [BLOB_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#blob_entry) を使用すると、インターフェイスとインターフェイスに使用するフラグを指定できます。 テーブルを開いた後、コードはを `Read` 繰り返し呼び出して、 `ISequentialStream` BLOB からバイトを読み取ります。 このコードは、を呼び出して `Release` `MoveNext` 次のレコードを取得する前に、インターフェイスポインターを破棄するためにを呼び出します。

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

その後、次のコードによって使用されます。

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

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

BLOB データを処理するマクロの詳細については、「マクロ内の **列マップマクロ** 」 [と「OLE DB コンシューマーテンプレートのグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)<br/>
[OLE DB コンシューマーテンプレートのマクロとグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
