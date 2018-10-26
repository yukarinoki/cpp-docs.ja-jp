---
title: CAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
dev_langs:
- C++
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ac3ad9da312ba1723fd7201b804260e11a64660
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060698"
---
# <a name="caccessor-class"></a>CAccessor クラス

アクセサーの種類のいずれかを表します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ユーザー レコード クラスです。

## <a name="remarks"></a>Remarks

レコードがデータ ソースに静的にバインドされている場合に使用されます。 レコードには、バッファーが含まれています。 このクラスは、行セットに対して複数のアクセサーをサポートします。

構造と、データベースの種類がわかっている場合は、このアクセサーの型を使用します。

アクセサーには、メモリを指しているフィールドが含まれている場合 (など、`BSTR`またはインターフェイス) する必要があるメンバー関数を呼び出す解放されると、 [caccessorrowset::freerecordmemory](../../data/oledb/caccessorrowset-freerecordmemory.md)レコードが読み取られる次の前に。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)