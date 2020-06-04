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
ms.openlocfilehash: 2b30cef2baf8c13c5001e44901b984aa1293494d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212304"
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

解放する必要があるメモリ (`BSTR` やインターフェイスなど) を指すフィールドがアクセサーに含まれている場合は、次のレコードが読み取られる前に、メンバー関数[CAccessorRowset:: FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)を呼び出します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
