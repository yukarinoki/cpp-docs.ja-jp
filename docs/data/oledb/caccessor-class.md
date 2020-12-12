---
description: '詳細情報: CAccessor クラス'
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
ms.openlocfilehash: 26b03bc3f464ce606194d6835953c39969bde5de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319171"
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

## <a name="remarks"></a>解説

レコードがデータソースに静的にバインドされている場合に使用されます。 レコードにはバッファーが含まれています。 このクラスは、行セットに対して複数のアクセサーをサポートします。

このアクセサー型は、データベースの構造と型がわかっている場合に使用します。

解放する必要があるメモリ (インターフェイスやインターフェイスなど) を指すフィールドがアクセサーに含まれている場合は、 `BSTR` 次のレコードが読み取られる前にメンバー関数 [CAccessorRowset:: FreeRecordMemory](./caccessorrowset-class.md#freerecordmemory) を呼び出します。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
