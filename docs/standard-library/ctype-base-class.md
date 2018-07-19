---
title: ctype_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3def685a8cd108666b3e1b8be9314fc7585a9837
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844895"
---
# <a name="ctypebase-class"></a>ctype_base クラス

このクラスは、テンプレート クラス [ctype](../standard-library/ctype-class.md) のファセットの基底クラスとして機能します。 個々の文字または範囲全体の文字を分類またはテストするための列挙型を定義するために使用される ctype クラスの基底クラス。

## <a name="syntax"></a>構文

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>コメント

列挙マスクを定義します。 ヘッダー \<ctype.h> に宣言されている同様の関数で定義されているように、列挙定数はそれぞれ、文字を分類する別の方法の特徴となっています。 定数は次のとおりです。

- **space** (関数 [isspace](../standard-library/locale-functions.md#isspace))

- **print** (関数 [isprint](../standard-library/locale-functions.md#isprint))

- **cntrl** (関数 [iscntrl](../standard-library/locale-functions.md#iscntrl))

- **upper** (関数 [isupper](../standard-library/locale-functions.md#isupper))

- **lower** (関数 [islower](../standard-library/locale-functions.md#islower))

- **digit** (関数 [isdigit](../standard-library/locale-functions.md#isdigit))

- **punct** (関数 [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (関数 [isxdigit](../standard-library/locale-functions.md#isxdigit))

- **alpha** (関数 [isalpha](../standard-library/locale-functions.md#isalpha))

- **alnum** (関数 [isalnum](../standard-library/locale-functions.md#isalnum))

- **graph** (関数 [isgraph](../standard-library/locale-functions.md#isgraph))

これらの定数を OR 演算することで、分類の組み合わせを特徴付けることができます。 具体的には、常に真であるが**alnum** = = (**アルファ** &#124; **桁**\)と**グラフ** \=\= \( **alnum** &#124; **punct**)。

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
