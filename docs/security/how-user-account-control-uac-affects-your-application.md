---
description: '詳細情報: ユーザーアカウント制御 (UAC) がアプリケーションに与える影響'
title: 'ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響'
ms.date: 11/19/2018
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
ms.openlocfilehash: 64196e0cac0a5b4edcf0b24fd95df2e5291ec45a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320067"
---
# <a name="how-user-account-control-uac-affects-your-application"></a>ユーザー アカウント制御 (UAC: User Account Control) がアプリケーションに与える影響

ユーザー アカウント制御 (UAC: User Account Control) は、限られた特権をユーザー アカウントに付与する Windows Vista の機能です。 UAC の詳細については、以下のサイトを参照してください。

- [最小限の特権を持つ環境におけるアプリケーションの開発者向けベストプラクティスとガイドライン](/windows/win32/uxguide/winenv-uac)

## <a name="building-projects-after-enabling-uac"></a>UAC を有効にした後のプロジェクトのビルド

UAC を無効にした状態で Windows Vista で Visual Studio C++ プロジェクトをビルドし、後で UAC を有効にする場合は、プロジェクトをクリーンにしてリビルドし、正常に動作するようにする必要があります。

## <a name="applications-that-require-administrative-privileges"></a>管理特権を必要とするアプリケーション

既定では、Visual C++ リンカーは、の実行レベルがのアプリケーションのマニフェストに UAC フラグメントを埋め込み `asInvoker` ます。 正しく実行するためにアプリケーションが管理特権を必要とする場合 (たとえば、アプリケーションがレジストリの HKLM ノードを変更する場合、または Windows ディレクトリなどのディスクの保護領域に書き込みを行う場合)、アプリケーションを変更する必要があります。

最初のオプションでは、マニフェストの UAC フラグメントを変更して実行レベルを *requireAdministrator* に変更します。 これにより、アプリケーションは実行前に管理資格情報を求めてユーザーにプロンプトを表示するようになります。 この方法の詳細については、「 [/MANIFESTUAC (UAC 情報をマニフェストに埋め込む)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md)」を参照してください。

2 番目は、`/MANIFESTUAC:NO` リンカー オプションを指定してマニフェストに UAC フラグメントを組み込まない方法です。 この場合、アプリケーションは仮想実行されます。 レジストリまたはファイル システムに変更を加えた場合、その変更はすべてアプリケーションの終了後に失われます。

UAC が有効な場合と無効な場合、またアプリケーションに UAC マニフェストがある場合とない場合のアプリケーションの動作の違いを次のフローチャートで説明します。

![Windows ローダーの動作](media/uacflowchart.png "Windows ローダーの動作")

## <a name="see-also"></a>関連項目

[セキュリティのベストプラクティス](security-best-practices-for-cpp.md)
