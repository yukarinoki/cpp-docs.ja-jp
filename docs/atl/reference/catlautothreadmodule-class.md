---
title: CAtlAutoThreadModule クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: f4bd1071380bf3e31c69c593c5db81112fdf21de
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168307"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule クラス

このクラスは、スレッドプールされたアパートメントモデルの COM サーバーを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>解説

`CAtlAutoThreadModule`[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)から派生し、スレッドプールされたアパートメントモデルの COM サーバーを実装します。 `CAtlAutoThreadModule`[CComApartment](../../atl/reference/ccomapartment-class.md)を使用して、モジュール内の各スレッドのアパートメントを管理します。

[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)をクラスファクトリとして指定するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)マクロを使用する必要があります。 次に、などのから`CAtlAutoThreadModuleT`派生したクラスの1つの`CAtlAutoThreadModule`インスタンスを追加する必要があります。 次に例を示します。

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> このクラスは、古い[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)クラスを置き換えます。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="see-also"></a>関連項目

[CAtlAutoThreadModuleT クラス](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
