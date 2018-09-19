---
title: プロジェクト ビルド エラー PRJ0036 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0036
dev_langs:
- C++
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32b73fb8d86ff537912218ea35089382a93aec4c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065193"
---
# <a name="project-build-error-prj0036"></a>プロジェクト ビルド エラー PRJ0036

Web 配置ツールの ' Additional Files' プロパティには、無効なエントリが含まれています。

Web 配置のプロパティ ページで追加のファイル プロパティには、マクロ評価の問題の可能性があるため、エラーが含まれています。 このエラーにあるパス形式が正しくない、文字またはファイル パスでは無効な文字の組み合わせを含むもします。

このエラーを解決するのには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。

このエラーは、参照されるファイルのいずれかが存在しないことを意味する可能性がありますもします。