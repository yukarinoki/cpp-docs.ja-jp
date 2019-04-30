---
title: コンパイラの警告 (レベル 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: 21873a883b19924ce3ef41511d65f8ae640875f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401723"
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

このサンプルの出力は次の注意:**終了タグ 'member' は、開始タグ 'summary' と一致しません。**

このサンプルで問題なの終了タグは\<概要 > が不完全で、コンパイラがそれを認識しないと、\<概要 > 終了タグ。  \<メンバー > タグは、/doc のコンパイルごとに、コンパイラによって .xdc ファイルに埋め込まれています。  ここで問題なはそのため、終了タグ\</member >、コンパイラが処理される前の開始タグと一致しません (\<概要 >。