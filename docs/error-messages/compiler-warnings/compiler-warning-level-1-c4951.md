---
title: コンパイラの警告 (レベル 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: d94347df17bac01334cfd85c2bd9f6c8a98b5fc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174597"
---
# <a name="compiler-warning-level-1-c4951"></a>コンパイラの警告 (レベル 1) C4951

> プロファイルデータが収集された後、'*function*' が編集されました。関数のプロファイルデータは使用されません

[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)への入力モジュールの関数が編集されたため、プロファイル データが無効になりました。 入力モジュールは、 **/LTCG:PGINSTRUMENT** の後に再コンパイルされ、 */LTCG:PGINSTRUMENT*の操作時にモジュールに含まれていたものとは異なる制御フローを使用した関数 ( **function** ) が含まれています。

これは、情報提供の警告です。 この警告を解決するには、 **/LTCG:PGINSTRUMENT**を実行してすべてのテストを再実行し、 **/LTCG:PGOPTIMIZE**を実行します。

**/LTCG:PGOPTIMIZE** が使用されていた場合、この警告はエラーに置き換わることがあります。
