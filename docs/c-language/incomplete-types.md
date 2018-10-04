---
title: 不完全な型 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae26bf4f3e036e6e71acc090c174638133d2e881
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759607"
---
# <a name="incomplete-types"></a>不完全な型

"*不完全な型*" とは、識別子を記述する型でありながら、識別子のサイズを決定するために必要な情報が欠けている型です。 不完全な型には次のようなものがあります。

- メンバーがまだ指定されていない構造体型。

- メンバーがまだ指定されていない共用体型。

- 次元がまだ指定されていない配列型。

**void** 型は、完全にすることのできない不完全な型です。 不完全な型を完全にするには、欠けている情報を指定します。 次の例では、不完全な型を作成する方法と完全にする方法について説明します。

- 不完全な構造体型を作成するには、メンバーを指定しないで構造体型を宣言します。 この例では、`ps` ポインターは `student` という不完全な構造体型を指しています。

    ```C
    struct student *ps;
    ```

- 不完全な構造体型を完全にするには、後で同じスコープ内で、メンバーを指定して同じ構造体型を宣言します。

    ```C
    struct student
    {
        int num;
    }                   /* student structure now completed */
    ```

- 不完全な配列型を作成するには、繰り返し回数を指定しないで配列型を宣言します。 例:

    ```C
    char a[];  /* a has incomplete type */
    ```

- 不完全な配列型を完全にするには、後で同じスコープ内で、繰り返し回数を指定して同じ名前を宣言します。

    ```C
    char a[25]; /* a now has complete type */
    ```

## <a name="see-also"></a>参照

[宣言と型](../c-language/declarations-and-types.md)