---
title: FactoryCacheFlags 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 250c8c8e7ade72bd1a9cd63f0b515774058f0723
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214007"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 列挙型

ファクトリオブジェクトをキャッシュするかどうかを決定します。

## <a name="syntax"></a>構文

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>解説

既定では、[モジュール](module-class.md)オブジェクトを作成するときに、ファクトリキャッシュポリシーが[ModuleType](moduletype-enumeration.md)テンプレートパラメーターとして指定されます。 このポリシーをオーバーライドするには、ファクトリオブジェクトを作成するときに**FactoryCacheFlags**値を指定します。

|||
|-|-|
|`FactoryCacheDefault`|`Module` オブジェクトのキャッシュポリシーが使用されます。|
|`FactoryCacheEnabled`|`Module` オブジェクトの作成に使用される `ModuleType` テンプレートパラメーターに関係なく、ファクトリキャッシュを有効にします。|
|`FactoryCacheDisabled`|`Module` オブジェクトの作成に使用される `ModuleType` テンプレートパラメーターに関係なく、ファクトリキャッシュを無効にします。|

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
