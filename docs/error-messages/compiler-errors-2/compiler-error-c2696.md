---
title: コンパイラエラー C2696
ms.date: 11/04/2016
f1_keywords:
- C2696
helpviewer_keywords:
- C2696
ms.assetid: 6c6eb7df-1230-4346-9a73-abf14c20785d
ms.openlocfilehash: f6af217dbcd871ac4edd1852042144802388545b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216090"
---
# <a name="compiler-error-c2696"></a>コンパイラエラー C2696

マネージド型 ' type ' の一時オブジェクトを作成することはできません

アンマネージプログラムでへの参照を行う **`const`** と、コンパイラがコンストラクターを呼び出し、スタックに一時オブジェクトを作成します。 ただし、マネージクラスをスタックに作成することはできません。

C2696 は、互換性のために残されているコンパイラオプション **/clr: oldSyntax**を使用してのみ到達可能です。
