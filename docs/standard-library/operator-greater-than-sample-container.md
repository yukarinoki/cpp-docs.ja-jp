---
description: '詳細情報: operator &gt; ( &lt; サンプルコンテナー &gt; )'
title: operator&gt; (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: 4a8282b3cac493bbf0c2bcb24b8db44df45168f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114963"
---
# <a name="operatorgt-ltsample-containergt"></a>operator&gt; (&lt;sample container&gt;)

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

Overloads **演算子>** クラステンプレート [コンテナー](../standard-library/sample-container-class.md)の2つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`right < left` が返されます。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)
