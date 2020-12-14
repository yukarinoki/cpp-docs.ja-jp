---
description: '詳細については、次を参照してください: FactoryCacheFlags 列挙型'
title: FactoryCacheFlags 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 68a86049bf1f6287a84ae4df2e27dbe3c63c91c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198506"
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

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
