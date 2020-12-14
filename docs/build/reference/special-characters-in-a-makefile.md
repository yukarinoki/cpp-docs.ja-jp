---
description: '詳細情報: メイクファイルの特殊文字'
title: メイクファイルの特殊文字
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: 22b8f6dd82191c88a23eaf1dabb551d468293a42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224674"
---
# <a name="special-characters-in-a-makefile"></a>メイクファイルの特殊文字

NMAKE の特殊文字をリテラル文字として使用するには、その前にカレット (^) を配置します。 NMAKE は、他の文字の前にあるキャレットを無視します。 その特殊文字は次のとおりです。

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

引用符で囲まれた文字列内のキャレット (^) は、リテラルのキャレット文字として扱われます。 行の末尾にあるカレットによって、リテラルの改行文字が文字列またはマクロに挿入されます。

マクロでは、バックスラッシュ ( \\ ) の後に改行文字が続くと、スペースで置き換えられます。

コマンドでは、パーセント記号 (%)はファイル指定子です。 コマンドで% を文字どおり表現するには、2つのパーセント記号 (%%) を指定します。1つの場所にあります。 他の状況では、NMAKE は1つの% を文字どおりに解釈しますが、double%% を1% として解釈します。 したがって、リテラル%% を表すには、3つのパーセント記号、%%%、または4パーセント記号を指定してください。%%%%。

コマンドでドル記号 ($) をリテラル文字として使用するには、2つのドル記号 ($ $) を指定します。 このメソッドは、^ $ が動作する他の状況でも使用できます。

## <a name="see-also"></a>関連項目

[メイクファイルの内容](contents-of-a-makefile.md)
