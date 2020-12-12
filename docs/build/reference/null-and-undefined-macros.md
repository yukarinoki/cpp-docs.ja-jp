---
description: 詳細については、「Null マクロと未定義マクロ」を参照してください。
title: Null マクロと未定義マクロ
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 639afda727f1ebb1f4d7d602ed7cf01d6c914a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209725"
---
# <a name="null-and-undefined-macros"></a>Null マクロと未定義マクロ

Null マクロと未定義マクロの両方が null 文字列に展開されますが、null 文字列として定義されたマクロは、前処理式で定義されていると見なされます。 マクロを null 文字列として定義するには、コマンドラインまたはコマンドファイルの等号 (=) の後にスペースまたはタブを除く文字を指定しないで、null 文字列または定義を二重引用符 ("") で囲みます。 マクロを未定義にするには、を使用し **ます。UNDEF。** 詳細については、「 [メイクファイルのプリプロセスディレクティブ](makefile-preprocessing-directives.md)」を参照してください。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](defining-an-nmake-macro.md)
