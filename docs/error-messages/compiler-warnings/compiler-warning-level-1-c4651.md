---
description: '詳細情報: コンパイラの警告 (レベル 1) C4651'
title: コンパイラの警告 (レベル 1) C4651
ms.date: 11/04/2016
f1_keywords:
- C4651
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
ms.openlocfilehash: 319d08799ed9494a5ef1d4d7b663fb8ec7b303e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318859"
---
# <a name="compiler-warning-level-1-c4651"></a>コンパイラの警告 (レベル 1) C4651

プリコンパイル済みヘッダーに対して ' definition ' が指定されましたが、現在のコンパイル用ではありません

定義はプリコンパイル済みヘッダーが生成されたときに指定されましたが、このコンパイルでは指定されませんでした。

定義はプリコンパイル済みヘッダー内で有効になりますが、コードの残りの部分には適用されません。

プリコンパイル済みヘッダーが/DSYMBOL でビルドされた場合、/Yu コンパイルに/DSYMBOL. がない場合、コンパイラはこの警告を生成します。  /DSYMBOL を/Yu コマンドラインに追加すると、この警告が解決されます。
