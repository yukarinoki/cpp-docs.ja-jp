---
description: 詳細については、「プロジェクトビルドエラー PRJ0008」を参照してください。
title: プロジェクト ビルド エラー PRJ0008
ms.date: 11/04/2016
f1_keywords:
- PRJ0008
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
ms.openlocfilehash: 2ae4952dfd3e5c5f53a3f549536598402ce1fd48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343913"
---
# <a name="project-build-error-prj0008"></a>プロジェクト ビルド エラー PRJ0008

ファイル ' file ' を削除できませんでした。

**ファイルが別のプロセスによって開かれていないこと、および書き込み禁止になっていないことを確認してください。**

再構築またはクリーン中に、Visual C++ によってビルドのすべての既知の中間ファイルと出力ファイルが削除されます。また、 [[全般構成設定] プロパティページ](../../build/reference/general-property-page-project.md)の [**クリーン時に削除する拡張機能**] プロパティで、ワイルドカードの指定を満たすファイルもすべて削除されます。

Visual C++ がファイルを削除できない場合は、このエラーが表示されます。 このエラーを解決するには、ビルドを実行するユーザー用にファイルとそのディレクトリを書き込み可能にします。
