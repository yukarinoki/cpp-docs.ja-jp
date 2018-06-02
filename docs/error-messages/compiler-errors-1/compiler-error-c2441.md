---
title: コンパイラ エラー C2441 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d4224d9090f3ace43f61a10c599fafa78d21600
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705281"
---
# <a name="compiler-error-c2441"></a>コンパイラ エラー C2441

> '*変数*': __declspec(process) と共に宣言されたシンボルで const を指定する必要があります: 純粋モード

## <a name="remarks"></a>コメント

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

既定では、変数は、アプリケーション ドメインごと **/clr: 純粋な**します。 変数のマーク`__declspec(process)` **/clr: 純粋な**が 1 つのアプリケーション ドメインで変更し、別の読み取り場合に発生したエラーを生じやすくなります。

コンパイラが 1 つのプロセス変数ではそのため、 `const`  **/clr: 純粋な**、すべてのアプリケーション ドメインでのみ読み取りそれらを作成します。

詳細については、次を参照してください。[プロセス](../../cpp/process.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。

## <a name="example"></a>例

次の例では、C2441 を生成します。

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```