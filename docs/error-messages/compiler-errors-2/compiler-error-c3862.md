---
title: コンパイラ エラー C3862 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b21e457feb6d090e4abaf531293987eb3504457
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704972"
---
# <a name="compiler-error-c3862"></a>コンパイラ エラー C3862

> '*関数*':/clr でアンマネージ関数をコンパイルできません:/clr:pure または/clr:safe

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

使用してコンパイル **/clr: 純粋な**または **/clr:safe**はイメージとネイティブ (アンマネージ) コードを含まない、MSIL のみイメージを生成します。  したがって、使用することはできません、`unmanaged`プラグマ、 **/clr: 純粋な**または **/clr:safe**コンパイルします。

詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)です。

## <a name="example"></a>例

次の例では、C3862 が生成されます。

```cpp
// C3862.cpp
// compile with: /clr:pure /c
#pragma unmanaged
void f() {}   // C3862
```