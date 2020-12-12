---
description: '詳細情報: コンパイラの警告 (レベル 1) C4951'
title: コンパイラの警告 (レベル 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: effb1f5af0c406de002b5c0b8522e7c58a2424a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327969"
---
# <a name="compiler-warning-level-1-c4951"></a>コンパイラの警告 (レベル 1) C4951

> プロファイルデータが収集された後、'*function*' が編集されました。関数のプロファイルデータは使用されません

[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)への入力モジュールの関数が編集されたため、プロファイル データが無効になりました。 入力モジュールは、 **/LTCG:PGINSTRUMENT** の後に再コンパイルされ、*/LTCG:PGINSTRUMENT* の操作時にモジュールに含まれていたものとは異なる制御フローを使用した関数 ( **function** ) が含まれています。

これは、情報提供の警告です。 この警告を解決するには、 **/LTCG:PGINSTRUMENT** を実行してすべてのテストを再実行し、 **/LTCG:PGOPTIMIZE** を実行します。

**/LTCG:PGOPTIMIZE** が使用されていた場合、この警告はエラーに置き換わることがあります。
