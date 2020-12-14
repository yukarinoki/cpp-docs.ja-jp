---
description: '詳細情報: NMAKE マクロの定義'
title: NMAKE マクロの定義
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 133e05cac2a236a38f6b2d1e719f1b66fd73760d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201639"
---
# <a name="defining-an-nmake-macro"></a>NMAKE マクロの定義

## <a name="syntax"></a>構文

```

macroname=string
```

## <a name="remarks"></a>解説

*Macroname* は、文字、数字、アンダースコア (_) を1024文字まで組み合わせたもので、大文字と小文字が区別されます。 *Macroname* には、呼び出されたマクロを含めることができます。 *Macroname* が呼び出されたマクロだけで構成される場合は、呼び出されるマクロを null または未定義にすることはできません。

には、 `string` 0 個以上の任意の文字列を指定できます。 Null 文字列には、0文字またはスペースまたはタブのみが含まれます。 には、 `string` マクロ呼び出しを含めることができます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[マクロの特殊文字](special-characters-in-macros.md)

[Null マクロと未定義マクロ](null-and-undefined-macros.md)

[マクロを定義する場所](where-to-define-macros.md)

[マクロ定義の優先順位](precedence-in-macro-definitions.md)

## <a name="see-also"></a>関連項目

[マクロと NMAKE](macros-and-nmake.md)
