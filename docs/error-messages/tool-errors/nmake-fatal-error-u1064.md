---
title: NMAKE の致命的なエラー U1064 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5573943fc2c274d48768933a634b2c052361a8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE の致命的なエラー U1064
MAKEFILE が見つかりません、また指定したターゲット  
  
 メイクファイルまたはターゲット (nmake の) のコマンドラインが指定されませんでしたし、現在のディレクトリにはメイクファイルをという名前のファイルが含まれていませんでした。  
  
 NMAKE では、メイクファイルまたはコマンド ライン ターゲット (または両方) が必要です。 Nmake メイクファイルを使用できるようにするには、/F オプションを指定するか、現在のディレクトリのメイクファイルをという名前のファイルを配置します。 NMAKE は、メイクファイルが指定されていない場合は、推論規則を使用して、コマンドラインのターゲットを作成できます。