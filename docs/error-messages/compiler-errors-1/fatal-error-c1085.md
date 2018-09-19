---
title: 致命的なエラー C1085 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1085
dev_langs:
- C++
helpviewer_keywords:
- C1085
ms.assetid: f2766365-d09b-4299-8a98-12e5aca98568
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab28c633ac7579e39f89d94d1c50e20cc156004a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043730"
---
# <a name="fatal-error-c1085"></a>致命的なエラー C1085

Filetype ファイルを書き込むことはできません 'file': メッセージ。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ドライブとは、読み取り専用です。

1. ドライブがいっぱいです。

1. 共有違反です。

1. "ファイル番号が正しくありません" というメッセージが表示される場合は、ファイルがバックグラウンドでのコンパイル中にフォアグラウンドで閉じられている可能性があります。