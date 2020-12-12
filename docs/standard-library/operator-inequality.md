---
description: '詳細については、次を参照してください: operator! ='
title: operator!=
ms.date: 11/04/2016
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
ms.openlocfilehash: 3b5efe9cc1c3157becd9afe4cf5c4e8020ec9e0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297058"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

`operator!=`クラステンプレート[コンテナー](../standard-library/sample-container-class.md)の2つのオブジェクトを比較するためのオーバーロード。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>戻り値

`!(left == right)` が返されます。

## <a name="see-also"></a>関連項目

[\<sample container>](../standard-library/sample-container.md)
