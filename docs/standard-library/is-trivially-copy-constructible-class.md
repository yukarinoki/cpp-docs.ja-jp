---
title: is_trivially_copy_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1924b82f7c3035ea2aecb463199558c9ead45c91
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102066"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible クラス

型に自明なコピー コンストラクターが含まれるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*は自明なコピー コンス トラクターを持つ、それ以外の場合は false を保持するクラスです。

クラスのコピー コンス トラクター *T*は暗黙的に宣言しても、クラスに自明*T* 、仮想関数または仮想基底クラス、すべての直接基本クラスのない*T*が自明なコピー コンス トラクターは、クラス型のすべての非静的データ メンバーのクラスに自明なコピー コンス トラクターがあるし、クラスの型配列のすべての非静的データ メンバーのクラスが自明なコピー コンス トラクターを持ちます。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
