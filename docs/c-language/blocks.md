---
title: ブロック | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function definitions, blocks in code
- blocks
- compound statements
- statements, compound
ms.assetid: be231a92-c712-464e-ae25-a4becb20f7f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 309e6c017587a2dd3cdc80cd55ffec82751dedd3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380941"
---
# <a name="blocks"></a>ブロック
中かっこ (**{ }**) で囲まれた一連の宣言、定義、ステートメントを "ブロック" といいます。 その 1 つは、1 つ以上のステートメントで構成される "複合ステートメント" です (「[複合ステートメント](../c-language/compound-statement-c.md)」を参照)。 もう 1 つの "関数定義" は、複合ステートメント (関数本体) とその関数のヘッダー (関数名、戻り値の型、仮パラメーター) で構成されます。 ブロック内に他のブロックが挿入された状態を "入れ子" といいます。  
  
 複合ステートメントはすべて中かっこで囲まれますが、中かっこで囲まれたすべてが複合ステートメントではないことに注意してください。 たとえば、配列、構造体、または列挙体の要素を指定する際に中かっこで囲む場合がありますが、これらは複合ステートメントではありません。  
  
## <a name="see-also"></a>参照  
 [ソース ファイルとソース プログラム](../c-language/source-files-and-source-programs.md)