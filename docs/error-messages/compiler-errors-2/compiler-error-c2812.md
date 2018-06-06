---
title: コンパイラ エラー C2812 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5469e4f7be3c164cc63fa30f5069009846be48
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705024"
---
# <a name="compiler-error-c2812"></a>コンパイラ エラー C2812

> \#インポートは/clr でサポートされていません:/clr:pure および/clr:safe

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

[#import ディレクティブ](../../preprocessor/hash-import-directive-cpp.md)でサポートされていない **/clr: 純粋な**と **/clr:safe**ため`#import`ネイティブ コンパイラのサポート ライブラリの使用が必要です。

## <a name="example"></a>例

次の例では、C2812 を生成します。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```