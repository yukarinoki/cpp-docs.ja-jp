---
title: メンバー アクセス
ms.date: 11/04/2016
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
ms.openlocfilehash: 12ea612625e21a8a13021b75e92f3752b0b5ce80
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179420"
---
# <a name="member-access"></a>メンバー アクセス

クラスメンバーアクセスは、メンバーアクセス演算子 ( **->** ) をオーバーロードすることによって制御できます。 この演算子は、この使用方法では単項演算子と見なされ、オーバーロードされる演算子関数は、クラス メンバー関数である必要があります。 したがって、このような関数の宣言は次のとおりです。

## <a name="syntax"></a>構文

```
class-type *operator->()
```

## <a name="remarks"></a>解説

ここで、*クラス型*は、この演算子が属するクラスの名前です。 メンバー アクセス演算子関数は、非静的メンバー関数である必要があります。

この演算子は、逆参照やカウントの使用の前にポインターを検証する "スマート ポインター" を実装するために使用されます (多くの場合はポインターの逆参照演算子と共に)。

**.** メンバーアクセス演算子をオーバーロードすることはできません。

## <a name="see-also"></a>参照

[演算子のオーバーロード](../cpp/operator-overloading.md)
