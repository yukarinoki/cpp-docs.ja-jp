---
title: コンパイラの警告 (レベル 1) C4399 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aedad6aed07a6056f74ad338037a7268c722627f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703721"
---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399

> '*シンボル*': プロセスごとのシンボルは/clr でコンパイルされるときにマークしないで: 純粋な

## <a name="remarks"></a>コメント

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

ネイティブ イメージまたはネイティブ モードと CLR コンストラクトを使用してイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、コンパイル時に **/clr** (いない **/clr: 純粋な**) を削除または`__declspec(dllimport)`です。

## <a name="example"></a>例

次の例では、C4399 を生成します。

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```