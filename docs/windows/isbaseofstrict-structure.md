---
title: IsBaseOfStrict 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 137f572f01d4aa72b9141c3ca172426fdb575b48
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169525"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <
   typename Base,
   typename Derived
>

struct IsBaseOfStrict;
template <
   typename Base
>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>パラメーター

*ベース*<br/>
基本データ型。

*派生*<br/>
派生型。

## <a name="remarks"></a>Remarks

一方の型がもう一方の型の基本クラスであるかどうかをテストします。

最初のテンプレートが生じる場合の基本型から派生する型かどうかをテストする`true`または`false`します。 2 番目のテンプレートはから派生した型自体には、常に生成するかどうかをテストする`false`します。

## <a name="members"></a>メンバー

### <a name="public-constants"></a>パブリック定数

名前                            | 説明
------------------------------- | --------------------------------------------------
[Isbaseofstrict::value](#value) | 1 つの型が別のベースであるかどうかを示します。

## <a name="inheritance-hierarchy"></a>継承階層

`IsBaseOfStrict`

## <a name="requirements"></a>要件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="value"></a>Isbaseofstrict::value

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Remarks

1 つの型が別のベースであるかどうかを示します。

`value` `true`場合型`Base`型の基本クラスは、 `Derived`、それ以外の場合は`false`します。
