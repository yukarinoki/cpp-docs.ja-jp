---
title: プロジェクトのビルドの警告 PRJ0041 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7677c5718783065f64e52f98f7ddbed76e905d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038140"
---
# <a name="project-build-warning-prj0041"></a>プロジェクト ビルドの警告 PRJ0041

見つかりませんファイル 'file' の依存関係の依存関係。 プロジェクトでは、ビルドすることが、このファイルが見つかるまで期限切れにします。

ファイル (リソース ファイルまたは.idl/.odl ファイル、たとえばに含まれている include ステートメントが、プロジェクト システムを解決できませんでした。

プロジェクト システムがプリプロセッサ ステートメント (たとえば #if) を処理できないため、問題が発生したステートメント実際にはできません、ビルドの一部。

この警告を解決するには、.rc ファイル内のすべての不要なコードを削除するか、適切な名前のプレース ホルダー ファイルを追加します。