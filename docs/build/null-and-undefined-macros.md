---
title: Null マクロと未定義マクロ
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: cf2dce2132cc1e7065cb0b93f1debd403f7a8342
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417230"
---
# <a name="null-and-undefined-macros"></a>Null マクロと未定義マクロ

Null の文字列を null と未定義マクロの展開が、null 文字列として定義されているマクロは、プリプロセス式で定義されていると見なされます。 Null を文字列としてマクロを定義する指定文字がないのでは、コマンドラインまたはコマンド ファイルを等号 (=) 後にスペースまたはタブを除くし、null 文字列または定義を二重引用符で囲みます ("")。 マクロの定義を解除するには使用 **!UNDEF します。** 詳細については、次を参照してください。[メイクファイルのプリプロセス ディレクティブ](../build/makefile-preprocessing-directives.md)します。

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](../build/defining-an-nmake-macro.md)
