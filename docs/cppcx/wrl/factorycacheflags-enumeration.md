---
title: FactoryCacheFlags 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 3381b2bcfcbf298270b547199ae614291855a2f7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843275"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 列挙型

ファクトリオブジェクトをキャッシュするかどうかを決定します。

## <a name="syntax"></a>構文

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>解説

既定では、[モジュール](module-class.md)オブジェクトを作成するときに、ファクトリキャッシュポリシーが[ModuleType](moduletype-enumeration.md)テンプレートパラメーターとして指定されます。 このポリシーをオーバーライドするには、ファクトリオブジェクトを作成するときに **FactoryCacheFlags** 値を指定します。

| ポリシー | [説明] |
|-|-|
|`FactoryCacheDefault`|オブジェクトのキャッシュポリシー `Module` が使用されます。|
|`FactoryCacheEnabled`|`ModuleType`オブジェクトの作成に使用されるテンプレートパラメーターに関係なく、ファクトリキャッシュを有効に `Module` します。|
|`FactoryCacheDisabled`|`ModuleType`オブジェクトの作成に使用されるテンプレートパラメーターに関係なく、ファクトリキャッシュを無効に `Module` します。|

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
