---
title: リンカー ツールの警告 LNK4014 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb86efbdc70342861a87a233ab687f7564cb48b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300060"
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014
メンバー オブジェクト"objectname"を見つけることができません。  
  
 LIB が見つかりませんでした。`objectname`ライブラリです。  
  
 **/Remove**と**抽出/** オプションを削除するか、ファイルにコピーがメンバー オブジェクトの完全名を必要とします。 完全な名前には、元のオブジェクト ファイルのパスが含まれています。 ライブラリ内のメンバー オブジェクトの完全名を使用して DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md)または LIB [/list](../../build/reference/managing-a-library.md)です。