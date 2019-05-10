---
title: コンテナー クラス::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 0ef4db1c14942fc896f10095ff2331648d27c820
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221645"
---
# <a name="container-classerase"></a>コンテナー クラス::erase

> [!NOTE]
> このトピックでは、Microsoft では、C++ドキュメントで使用されるコンテナーの機能の例として、C++標準ライブラリ。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

要素を消去します。

## <a name="syntax"></a>構文

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Remarks

最初のメンバー関数が指す被制御シーケンスの要素を削除する *_Where*します。 2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 どちらも、削除した要素の後に残る最初の要素を指定する反復子を返します。そのような要素が存在しない場合は、[end](../standard-library/container-class-end.md) を返します。

メンバー関数は、コピー操作が例外をスローする場合にのみ、例外をスローします。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
