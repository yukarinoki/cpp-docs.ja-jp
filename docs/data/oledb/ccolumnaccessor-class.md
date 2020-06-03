---
title: CColumnAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2a3b1dac51a8300a915a7177c36f15512b583fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212111"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor クラス

挿入されたコンシューマーコードを生成します。

## <a name="syntax"></a>構文

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>解説

挿入されたコードでは、すべての列が個別のアクセサーとしてバインドされます。 このクラスは挿入されたコードで使用されることに注意してください (たとえば、デバッグ時に発生する可能性があります) が、通常はこのクラスまたはメソッドを直接使用する必要はありません。

`CColumnAccessor` は、次のスタブメソッドを実装します。それぞれのメソッドは、他のアクセサークラスメソッドに機能します。

- コンストラクターを `CColumnAccessor` します。`CColumnAccessor` オブジェクトをインスタンス化し、初期化します。

- `CreateAccessor` によって、列のバインド構造にメモリが割り当てられ、列のデータメンバーが初期化されます。

- `BindColumns` アクセサーに列をバインドします。

- `SetParameterBuffer` は、パラメーターのバッファーを割り当てます。

- パラメーターエントリをパラメーターエントリ構造に追加する `AddParameter` ます。

- アクセサーに出力列があるかどうかを判断 `HasOutputColumns`

- アクセサーにパラメーターがあるかどうかを `HasParameters` によって判断されます。

- `BindParameters` 作成されたパラメーターを列にバインドします。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
