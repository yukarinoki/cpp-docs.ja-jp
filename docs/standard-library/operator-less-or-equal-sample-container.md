---
description: '詳細については、次を参照してください: operator &lt; = ( &lt; サンプルコンテナー &gt; )'
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
ms.openlocfilehash: 4455efcbd5b3ccca262265f44414b46d3e97f57d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337999"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;sample container&gt;)

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

Overloads **operator<=** クラステンプレート [コンテナー](../standard-library/sample-container-class.md)の2つのオブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`!(right < left)` が返されます。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)
