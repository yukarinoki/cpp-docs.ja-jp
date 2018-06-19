---
title: Null と未定義マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 494a084ee5ba1da29c132aa632b647b37f305855
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368471"
---
# <a name="null-and-undefined-macros"></a>Null マクロと未定義マクロ
Null と未定義の両方のマクロが null の文字列への展開が、null 文字列として定義されているマクロは、プリプロセス式で定義されていると見なされます。 マクロを定義する、null 文字列として、指定文字を含まないがコマンドラインまたはコマンド ファイルに等号 (=) の後のスペースまたはタブを除くし、null 文字列または定義を二重引用符で囲みます ("") です。 マクロを未定義を使用して **!UNDEF です。** 詳細については、次を参照してください。[メイクファイルのプリプロセス ディレクティブ](../build/makefile-preprocessing-directives.md)です。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)