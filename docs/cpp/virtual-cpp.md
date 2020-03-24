---
title: virtual (C++)
ms.date: 11/04/2016
f1_keywords:
- virtual_cpp
- virtual
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
ms.openlocfilehash: a8948594bade940834e041adc73d56cc7847acc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187506"
---
# <a name="virtual-c"></a>virtual (C++)

Virtual**キーワードは**、仮想関数または仮想基底クラスを宣言します。

## <a name="syntax"></a>構文

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>パラメーター

*型指定子*<br/>
仮想メンバー関数の戻り値の型を指定します。

*メンバー関数宣言子*<br/>
メンバー関数を宣言します。

*アクセス指定子*<br/>
基底クラス ( **public**、 **protected** 、または**private**) へのアクセスレベルを定義します。 は、 **virtual**キーワードの前または後に置くことができます。

*基底クラス名*<br/>
以前に宣言されたクラス型を識別します。

## <a name="remarks"></a>解説

詳細については、「[仮想関数](../cpp/virtual-functions.md)」を参照してください。

次のキーワードも参照してください: [class](../cpp/class-cpp.md)、 [private](../cpp/private-cpp.md)、 [public](../cpp/public-cpp.md)、 [protected](../cpp/protected-cpp.md)。

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)
