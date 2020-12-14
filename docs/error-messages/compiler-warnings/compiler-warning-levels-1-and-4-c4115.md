---
description: '詳細情報: コンパイラの警告 (レベル1および 4) C4115'
title: コンパイラの警告 (レベル 1 および 4) C4115
ms.date: 11/04/2016
f1_keywords:
- C4115
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
ms.openlocfilehash: f41dcdf16d541151384d50d004a55d6e1993ece0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234490"
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>コンパイラの警告 (レベル 1 および 4) C4115

'type': かっこの中で名前付きの型が使用されました

構造体、共用体、または列挙型を定義するための特定のシンボルが、かっこで囲まれた式の内部で定義されています。 定義のスコープが、予期せぬものとなる場合があります。

C の関数呼び出しでは、定義はグローバル スコープを持ちます。 C++ の呼び出しでは、定義は呼び出される関数と同じスコープを持ちます。

この警告は、かっこで囲まれた式ではない (プロトタイプなど) のかっこ内の宣言子によって引き起こされる場合もあります。

これは、ANSI 互換 (/Za) でコンパイルされた C++ プログラムと C プログラムではレベル 1 の警告です。 それ以外の場合はレベル 3 です。
