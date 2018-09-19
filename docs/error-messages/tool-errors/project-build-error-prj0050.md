---
title: プロジェクト ビルド エラー PRJ0050 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0050
dev_langs:
- C++
helpviewer_keywords:
- PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb3949ea0db2f1667aecf1aeeefd922b192cbf41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100592"
---
# <a name="project-build-error-prj0050"></a>プロジェクト ビルド エラー PRJ0050

出力を登録できませんでした。 レジストリを変更する適切なアクセス許可があることを確認してください。

Visual C ビルド システムは、(dll または .exe)、ビルドの出力を登録できませんでした。 レジストリの変更に管理者としてログオンする必要があります。

.Dll を作成する場合は、regsvr32.exe を使用して手動で .dll を登録しようとすることができます、このビルドが失敗した理由に関する情報を表示する必要があります。

.Dll を作成していない場合、エラーが発生したコマンドのビルド ログを確認します。