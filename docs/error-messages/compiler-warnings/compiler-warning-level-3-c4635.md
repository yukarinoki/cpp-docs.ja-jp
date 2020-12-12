---
description: '詳細情報: コンパイラの警告 (レベル 3) C4635'
title: コンパイラの警告 (レベル 3) C4635
ms.date: 11/04/2016
f1_keywords:
- C4635
helpviewer_keywords:
- C4635
ms.assetid: b2ba90de-c093-4a76-8076-b65878467574
ms.openlocfilehash: e885c501e4f10719618bb552c153dc13a481332d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168333"
---
# <a name="compiler-warning-level-3-c4635"></a>コンパイラの警告 (レベル 3) C4635

XML ドキュメント コメント対象: XML の形式が正しくありません: 理由

コンパイラは XML タグに何らかの問題を検出しました。  問題を修正して再コンパイルします

次の例では C4635 が生成されます。

```cpp
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

このサンプルの問題は、の終了タグの \<summary> 形式が適切ではなく、コンパイラが終了タグとして認識していないことです \<summary> 。  この \<member> タグは、すべての/doc コンパイルでコンパイラによって .xdc ファイルに埋め込まれます。  ここでの問題は、終了タグが、 \</member> コンパイラによって処理された前の開始タグ () と一致しないことです \<summary> 。
