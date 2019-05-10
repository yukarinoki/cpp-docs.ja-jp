---
title: operator&lt;= (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
ms.openlocfilehash: 78d49f82f39bc0e96f88ffdcad2cde8a20b0f123
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221382"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;sample container&gt;)

> [!NOTE]
> このトピックでは、Microsoft では、C++ドキュメントで使用されるコンテナーの機能の例として、C++標準ライブラリ。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

**operator<=** をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の 2 つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`!(right < left)` を返します。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)<br/>
