---
title: 'ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響'
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 3818b0ff7d4e4c551c41726dd44935beb5d32842
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448478"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響

ユーザー アカウント制御 (UAC: User Account Control) は、限られた特権をユーザー アカウントに付与する Windows Vista の機能です。 UAC の詳細については、以下のサイトを参照してください。

- [開発者のベスト プラクティスと、最低限の特権の環境でアプリケーションのガイドライン](/windows/desktop/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>UAC を有効にした後のプロジェクトのビルド

Visual Studio をビルドする場合C++プロジェクトに Windows Vista で UAC を無効に、後で UAC を有効にし、消去し、正常に動作するためにプロジェクトをリビルドする必要があります。

## <a name="applications-that-require-administrative-privileges"></a>管理特権を必要とするアプリケーション

既定では、Visual C リンカーは、アプリケーションの実行レベルでのマニフェストに UAC フラグメントを組み込みます`asInvoker`します。 正しく実行するためにアプリケーションが管理特権を必要とする場合 (たとえば、アプリケーションがレジストリの HKLM ノードを変更する場合、または Windows ディレクトリなどのディスクの保護領域に書き込みを行う場合)、アプリケーションを変更する必要があります。

最初のオプションは、実行レベルを変更するマニフェストの UAC フラグメントを変更するのには*requireAdministrator*します。 これにより、アプリケーションは実行前に管理資格情報を求めてユーザーにプロンプトを表示するようになります。 これを行う方法については、次を参照してください。 [/MANIFESTUAC (UAC 情報をマニフェスト)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md)します。

2 番目は、`/MANIFESTUAC:NO` リンカー オプションを指定してマニフェストに UAC フラグメントを組み込まない方法です。 この場合、アプリケーションは仮想実行されます。 レジストリまたはファイル システムに変更を加えた場合、その変更はすべてアプリケーションの終了後に失われます。

UAC が有効な場合と無効な場合、またアプリケーションに UAC マニフェストがある場合とない場合のアプリケーションの動作の違いを次のフローチャートで説明します。

![Windows ローダーの動作](media/uacflowchart.png "Windows ローダーの動作")

## <a name="see-also"></a>関連項目

[セキュリティ推奨事項](security-best-practices-for-cpp.md)
