---
title: 'ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響'
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 04bfc16f2d82863faca806d4cb8d5295104a0cc9
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52177044"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響

ユーザー アカウント制御 (UAC: User Account Control) は、限られた特権をユーザー アカウントに付与する Windows Vista の機能です。 UAC の詳細については、以下のサイトを参照してください。

- [開発者のベスト プラクティスと、最低限の特権の環境でアプリケーションのガイドライン](/windows/desktop/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>UAC を有効にした後のプロジェクトのビルド

UAC を無効にした状態で Windows Vista で Visual C++ プロジェクトをビルドし、後で UAC を有効にする場合は、正しく動作させるためにプロジェクトを消去して、リビルドする必要があります。

## <a name="applications-that-require-administrative-privileges"></a>管理特権を必要とするアプリケーション

既定では、Visual C リンカーは、アプリケーションの実行レベルでのマニフェストに UAC フラグメントを組み込みます`asInvoker`します。 正しく実行するためにアプリケーションが管理特権を必要とする場合 (たとえば、アプリケーションがレジストリの HKLM ノードを変更する場合、または Windows ディレクトリなどのディスクの保護領域に書き込みを行う場合)、アプリケーションを変更する必要があります。

最初のオプションは、実行レベルを変更するマニフェストの UAC フラグメントを変更するのには*requireAdministrator*します。 これにより、アプリケーションは実行前に管理資格情報を求めてユーザーにプロンプトを表示するようになります。 これを行う方法については、次を参照してください。 [/MANIFESTUAC (UAC 情報をマニフェスト)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md)します。

2 番目は、`/MANIFESTUAC:NO` リンカー オプションを指定してマニフェストに UAC フラグメントを組み込まない方法です。 この場合、アプリケーションは仮想実行されます。 レジストリまたはファイル システムに変更を加えた場合、その変更はすべてアプリケーションの終了後に失われます。

UAC が有効な場合と無効な場合、またアプリケーションに UAC マニフェストがある場合とない場合のアプリケーションの動作の違いを次のフローチャートで説明します。

![Windows ローダーの動作](media/uacflowchart.png "Windows ローダーの動作")

## <a name="see-also"></a>関連項目

[セキュリティ推奨事項](security-best-practices-for-cpp.md)
