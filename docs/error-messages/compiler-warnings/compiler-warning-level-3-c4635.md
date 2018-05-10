---
title: コンパイラの警告 (レベル 3) C4635 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4635
dev_langs:
- C++
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dcc4b7466ed53a187b7f34ec45084a94adb59b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4635"></a>コンパイラの警告 (レベル 3) C4635
XML ドキュメント コメント対象: XML の形式が正しくありません: 理由  
  
 コンパイラは XML タグに何らかの問題を検出しました。  問題を修正して再コンパイルします  
  
 次の例では C4635 が生成されます。  
  
```  
// C4635.cpp  
// compile with: /doc /clr /W3 /c  
/// <summary>     
/// The contents of the folder have changed.  
/// <summary/>   // C4635  
  
// try the following line instead  
// /// </summary>  
public ref class Test {};  
```  
  
 このサンプルの次の出力に注意してください: **'member' の終了タグが開始タグ 'summary' と一致しません。**  
  
 このサンプルでの問題は、終了タグの\<概要 > が不完全で、コンパイラが認識しないこととして、\<概要 > 終了タグ。  \<メンバー > タグは、/doc のコンパイルごとに、コンパイラによって .xdc ファイルに埋め込まれています。  そのため、ここでの問題は、終了タグ\</member >、コンパイラが処理される前の開始タグと一致しません (\<概要 >。