---
title: is_trivially_default_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73bdd8186f2ce56e4a6ecec0fa4f9468d9da8e8c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102708"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible クラス

型に自明な既定コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*が自明なコンス トラクター、それ以外の場合は false を保持するクラスです。

クラスの既定のコンス トラクター *Ty*は簡単では場合。

- 暗黙的に宣言された既定のコンス トラクターである

- クラスは、 *Ty*仮想関数がありません

- クラスは、 *Ty*仮想基底クラスがありません

- すべての直接の基底クラスの*Ty*自明なコンス トラクターがあります。

- クラス型のすべての非静的データ メンバーのクラスに自明なコンストラクターがある

- クラスの型配列のすべての非静的データ メンバーのクラスに自明なコンストラクターがある

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
