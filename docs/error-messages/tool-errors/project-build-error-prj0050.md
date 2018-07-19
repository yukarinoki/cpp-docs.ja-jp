---
title: プロジェクト ビルド エラー PRJ0050 |Microsoft ドキュメント
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
ms.openlocfilehash: 0ad17614f693e313190dba9cc767c023981dec34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318514"
---
# <a name="project-build-error-prj0050"></a>プロジェクト ビルド エラー PRJ0050
出力を登録できませんでした。 レジストリを変更する適切なアクセス許可があることを確認してください。  
  
 Visual C ビルド システムは、(dll または .exe)、ビルドの出力を登録できませんでした。 レジストリの変更に管理者としてログオンする必要があります。  
  
 .Dll を構築する場合は、regsvr32.exe を使用して手動で .dll を登録しようとすることができます、このビルドが失敗した理由に関する情報を表示する必要があります。  
  
 .Dll を作成していない場合、エラーが発生したコマンドのビルド ログを調べます。