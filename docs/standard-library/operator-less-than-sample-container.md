---
title: operator&lt; (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
ms.openlocfilehash: a286833d96e913a66240d25798e1cc230adf58b0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458726"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt; (&lt;sample container&gt;)

> [!NOTE]
> このトピックは、 C++ C++標準ライブラリで使用されているコンテナーの非機能例として、Microsoft ドキュメントに記載されています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

**operator<** をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の 2 つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`lexicographical_compare(left.begin, left.end, right.begin, right.end)` を返します。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)\
[初め](../standard-library/container-class-begin.md)\
[end](../standard-library/container-class-end.md)