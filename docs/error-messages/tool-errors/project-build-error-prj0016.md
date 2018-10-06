---
title: プロジェクト ビルド エラー PRJ0016 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01610f888d8afe275b0e52b86e4f4c678f896c9f
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820475"
---
# <a name="project-build-error-prj0016"></a>プロジェクト ビルド エラー PRJ0016

ユーザーのセキュリティ設定は、プロセスが作成されないようにします。 これらの設定は、構築するために必要です。

プロセスを使用してプロセスを作成するアクセス許可を持っていないユーザーのユーザーとしてログインしています。 このユーザー アカウントのアクセス許可レベルを変更するか、アカウント管理者にお問い合わせください。

このエラーは、次のレジストリ キーが設定されている場合にも発生します。

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

このエラーを解決するには、RestrictRun のキーを削除します。 このレジストリ キーが必要な場合は、追加**vcspawn.exe**キーのエントリの一覧にします。

このエラーのもう 1 つの原因は、ポリシーの設定は含まれていません VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun レジストリ キーの下でこのユーザー アカウントに許可されているウィンドウ プログラムとしてです。

詳細についてを参照してください。

- 使用されるナレッジ ベース記事 324153、 [ http://support.microsoft.com/default.aspx?scid=kb324153;](http://support.microsoft.com/default.aspx?scid=kb;324153)します。

- [システム ポリシーの設定に準拠する](https://msdn.microsoft.com/library/aa372139)、「許可された Windows アプリケーションだけを実行する」に関するセクション。