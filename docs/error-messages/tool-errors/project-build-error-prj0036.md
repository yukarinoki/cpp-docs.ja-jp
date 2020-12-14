---
description: 詳細については、「プロジェクトビルドエラー PRJ0036」を参照してください。
title: プロジェクト ビルド エラー PRJ0036
ms.date: 11/04/2016
f1_keywords:
- PRJ0036
helpviewer_keywords:
- PRJ0036
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
ms.openlocfilehash: 753c526d7d15a0d90bef71b7923a4353ed02b098
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240963"
---
# <a name="project-build-error-prj0036"></a>プロジェクト ビルド エラー PRJ0036

Web 配置ツールの "追加ファイル" プロパティに無効なエントリが含まれています。

マクロ評価の問題のために、Web 配置プロパティページの [追加ファイル] プロパティにエラーが含まれていました。 このエラーは、パスの形式が正しくないことを意味する場合もあります。これは、ファイルパスで無効な文字または文字の組み合わせが含まれていることを意味します。

このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 評価されたパスは、プロジェクトディレクトリからの絶対パスです。

このエラーは、参照されているファイルの1つが存在しないことを意味する場合もあります。
