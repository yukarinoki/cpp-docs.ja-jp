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
ms.openlocfilehash: 9313df5d75efa043f2fb9df6090c125de75a2636
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220261"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;sample container&gt;)

> [!NOTE]
> このトピックでは、Microsoft では、C++ドキュメントで使用されるコンテナーの機能の例として、C++標準ライブラリ。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

`operator==` をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の 2 つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

返します`left.`[サイズ](../standard-library/container-class-size.md) ` == right.size && equal(left.`[開始](../standard-library/container-class-begin.md)`, left.`[エンド](../standard-library/container-class-end.md)`, right.begin)`します。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)<br/>
