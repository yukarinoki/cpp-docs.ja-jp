---
title: RuntimeClassFlags 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 9fed5bb31b077288495a78aefcbd8401b3520bb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367227"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 構造体

[ランタイム クラス](runtimeclass-class.md)のインスタンスの型を格納します。

## <a name="syntax"></a>構文

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
[列挙値。](runtimeclasstype-enumeration.md)

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[RuntimeClassFlags::value 定数](#value-constant)|[列挙](runtimeclasstype-enumeration.md)値が含まれています。|

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassFlags`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a>クラスフラグ::値定数

[列挙](runtimeclasstype-enumeration.md)値を格納するフィールド。

```cpp
static const unsigned int value = flags;
```
