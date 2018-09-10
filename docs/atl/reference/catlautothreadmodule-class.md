---
title: CAtlAutoThreadModule クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b534190a4e7243f5192e6d703b056d8bcb327ca
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110644"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule クラス

このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Remarks

`CAtlAutoThreadModule` 派生した[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)し、スレッド プール、アパートメント モデルの COM サーバーを実装します。 `CAtlAutoThreadModule` 使用して[CComApartment](../../atl/reference/ccomapartment-class.md)モジュール内の各スレッド アパートメントを管理します。

使用する必要があります、 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread)を指定するオブジェクトのクラス定義でマクロ[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリとして。 派生したクラスの 1 つのインスタンスを追加する必要がありますし、`CAtlAutoThreadModuleT`など`CAtlAutoThreadModule`します。 例えば:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> このクラスは廃止された置換[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)クラス。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目

[CAtlAutoThreadModuleT クラス](../../atl/reference/catlautothreadmodulet-class.md)   
[IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)   
[モジュール クラス](../../atl/atl-module-classes.md)
