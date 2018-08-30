---
title: コンパイラの警告 (レベル 1) C4951 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e26c4bc176a54f063a3f9bce2faf451a9c0406f0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204236"
---
# <a name="compiler-warning-level-1-c4951"></a>コンパイラの警告 (レベル 1) C4951

> '*関数*' からプロファイル データが収集された関数のプロファイル データは使用されませんが編集されました

[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)への入力モジュールの関数が編集されたため、プロファイル データが無効になりました。 後で再コンパイルされた入力モジュール **/LTCG:PGINSTRUMENT**関数であり (*関数*)、別の時点で、モジュールが制御フローと、 **/LTCG:PGINSTRUMENT**操作。

これは、情報提供の警告です。 この警告を解決するには、 **/LTCG:PGINSTRUMENT**を実行してすべてのテストを再実行し、 **/LTCG:PGOPTIMIZE**を実行します。

**/LTCG:PGOPTIMIZE** が使用されていた場合、この警告はエラーに置き換わることがあります。