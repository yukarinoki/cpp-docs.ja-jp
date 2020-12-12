---
description: '詳細については、「コンテナークラス:: erase」を参照してください。'
title: コンテナー クラス::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 7e9d7747237a38c42bfb7a39c5d5e66cc8a44608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324868"
---
# <a name="container-classerase"></a>コンテナー クラス::erase

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの非機能例として、Microsoft C++ ドキュメントに記載されています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。

要素を消去します。

## <a name="syntax"></a>構文

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>解説

1つ目のメンバー関数は、 *_Where* が指す被制御シーケンスの要素を削除します。 2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 どちらも、削除した要素の後に残る最初の要素を指定する反復子を返します。そのような要素が存在しない場合は、[end](../standard-library/container-class-end.md) を返します。

メンバー関数は、コピー操作が例外をスローする場合にのみ、例外をスローします。

## <a name="see-also"></a>関連項目

[サンプルコンテナークラス](../standard-library/sample-container-class.md)
