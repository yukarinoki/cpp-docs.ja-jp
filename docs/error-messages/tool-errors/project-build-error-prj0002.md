---
title: プロジェクト ビルド エラー PRJ0002
ms.date: 08/27/2018
f1_keywords:
- PRJ0002
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
ms.openlocfilehash: 30680f5b26f3be5e7f9b48d18e82fca42ed65493
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192940"
---
# <a name="project-build-error-prj0002"></a>プロジェクト ビルド エラー PRJ0002

> '*コマンドライン*' からエラー結果が返されました。

コマンド*ライン*は、 **[プロパティページ]** ダイアログボックスのユーザー入力から作成されたもので、エラーコードを返しましたが、**出力**ウィンドウに情報が表示されません。

このエラーの解決策は、エラーが生成されたツールによって異なります。 MIDL の場合、/o (リダイレクト出力) が定義されていると、どのような問題が発生したかがわかります。

カスタムビルドステップやビルドイベントなど、エラー状態に関する情報がないバッチファイルも、このエラーの原因である可能性があります。
