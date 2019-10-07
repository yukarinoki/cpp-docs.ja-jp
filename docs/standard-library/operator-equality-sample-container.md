---
title: operator== (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: 168785abb09ca198435c301040d7628a6dd12b26
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460156"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;sample container&gt;)

> [!NOTE]
> このトピックは、 C++ C++標準ライブラリで使用されているコンテナーの非機能例として、Microsoft ドキュメントに記載されています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

`operator==` をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の 2 つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`left.`[size](../standard-library/container-class-size.md) ` == right.size && equal(left.`[begin](../standard-library/container-class-begin.md)`, left.`[end](../standard-library/container-class-end.md)`, right.begin)` を返します。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)
