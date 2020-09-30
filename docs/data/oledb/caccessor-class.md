---
title: CAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 032274d7dc85aa823cd28cf61e4606903f13ad9e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509563"
---
# <a name="caccessor-class"></a>CAccessor クラス

アクセサー型の1つを表します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ユーザーレコードクラス。

## <a name="remarks"></a>注釈

レコードがデータソースに静的にバインドされている場合に使用されます。 レコードにはバッファーが含まれています。 このクラスは、行セットに対して複数のアクセサーをサポートします。

このアクセサー型は、データベースの構造と型がわかっている場合に使用します。

解放する必要があるメモリ (インターフェイスやインターフェイスなど) を指すフィールドがアクセサーに含まれている場合は、 `BSTR` 次のレコードが読み取られる前にメンバー関数 [CAccessorRowset:: FreeRecordMemory](./caccessorrowset-class.md#freerecordmemory) を呼び出します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
