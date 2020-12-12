---
description: 詳細については、「プロジェクトビルドエラー PRJ0002」を参照してください。
title: プロジェクト ビルド エラー PRJ0002
ms.date: 08/27/2018
f1_keywords:
- PRJ0002
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
ms.openlocfilehash: b9f3d06a71183902c92102f12f665decdbf35a9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119422"
---
# <a name="project-build-error-prj0002"></a>プロジェクト ビルド エラー PRJ0002

> '*コマンドライン*' からエラー結果が返されました。

コマンド *ライン* は、[ **プロパティページ** ] ダイアログボックスのユーザー入力から作成されたもので、エラーコードを返しましたが、 **出力** ウィンドウに情報が表示されません。

このエラーの解決策は、エラーが生成されたツールによって異なります。 MIDL の場合、/o (リダイレクト出力) が定義されていると、どのような問題が発生したかがわかります。

カスタムビルドステップやビルドイベントなど、エラー状態に関する情報がないバッチファイルも、このエラーの原因である可能性があります。
