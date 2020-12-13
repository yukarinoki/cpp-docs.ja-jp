---
description: '詳細情報: CColumnAccessor クラス'
title: CColumnAccessor クラス
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 7551f39d34bb4f13b4ffae358db05aede2adb9e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335523"
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

- `CColumnAccessor` コンストラクター。オブジェクトをインスタンス化し、初期化し `CColumnAccessor` ます。

- `CreateAccessor` 列のバインド構造にメモリを割り当て、列のデータメンバーを初期化します。

- `BindColumns` アクセサーに列をバインドします。

- `SetParameterBuffer` パラメーターのバッファーを割り当てます。

- `AddParameter` パラメーターエントリをパラメーターエントリ構造体に追加します。

- `HasOutputColumns` アクセサーに出力列があるかどうかを判断します。

- `HasParameters` アクセサーにパラメーターがあるかどうかを判断します。

- `BindParameters` 作成されたパラメーターを列にバインドします。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
