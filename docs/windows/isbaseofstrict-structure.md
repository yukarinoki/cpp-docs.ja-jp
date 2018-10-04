---
title: IsBaseOfStrict 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
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
ms.openlocfilehash: 9fc41bdccf9cce3d455d4effd3541731929e5de2
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789268"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
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
