---
title: プロジェクト ビルド エラー PRJ0030 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf1c9137f8c4ed0d80955eef38b07ea86204a5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317659"
---
# <a name="project-build-error-prj0030"></a>プロジェクト ビルド エラー PRJ0030
マクロ拡張エラーです。 $ (マクロ) を超えました再帰 32 レベルを評価します。  
  
 マクロでは再帰では、このエラーが発生します。 たとえば、設定した場合、**中間ディレクトリ**プロパティ (を参照してください[[全般] プロパティ ページ (プロジェクト)](../../ide/general-property-page-project.md)) に $(IntDir)、再帰が発生します。  
  
 このエラーを解決するのには定義しませんマクロまたはマクロを定義するメッセージが表示されるプロパティ。