---
description: '詳細については、次を参照してください: operator = = ( &lt; サンプルコンテナー &gt; )'
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
ms.openlocfilehash: b2fb296feb76536c28dd45e631af8071efa16939
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337984"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;sample container&gt;)

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

`operator==`クラステンプレート[コンテナー](../standard-library/sample-container-class.md)の2つのオブジェクトを比較するためのオーバーロード。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`left.`[サイズ](../standard-library/container-class-size.md) `== right.size && equal(left.` の[開始](../standard-library/container-class-begin.md) `, left.` [位置](../standard-library/container-class-end.md)を返し `, right.begin)` ます。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)
