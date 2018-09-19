---
title: プロジェクト ビルド エラー PRJ0030 |Microsoft Docs
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
ms.openlocfilehash: 964fedd40f577a8b337c4ad0c20ba80d33ed2a23
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099923"
---
# <a name="project-build-error-prj0030"></a>プロジェクト ビルド エラー PRJ0030

マクロ拡張エラーです。 $ (マクロ) を超えました再帰 32 レベルを評価します。

このエラーは、マクロ内の再帰によって発生します。 たとえば、設定した場合、**中間ディレクトリ**プロパティ (を参照してください[[全般] プロパティ ページ (プロジェクト)](../../ide/general-property-page-project.md)) に $(IntDir)、再帰が。

このエラーを解決するのには、マクロまたはマクロの定義に使用するプロパティ定義されません。