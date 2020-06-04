---
title: プロジェクト ビルド エラー PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 0cab1e35a36ab78426923d60acafb5cdf2942469
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192745"
---
# <a name="project-build-error-prj0016"></a>プロジェクト ビルド エラー PRJ0016

ユーザーのセキュリティ設定により、プロセスを作成できません。 これらの設定は、ビルドに必要です。

プロセスを使用してプロセスを作成するアクセス許可を持たないユーザーとしてログインしています。 このユーザーアカウントのアクセス許可レベルを変更するか、アカウント管理者に連絡してください。

このエラーは、次のレジストリキーが設定されている場合にも発生する可能性があります。

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

このエラーを解決するには、RestrictRun キーを削除します。 このレジストリキーが必要な場合は、キーのエントリの一覧に**vcspawn**追加します。

このエラーのもう1つの原因は、ポリシー設定では、レジストリキーの下に VCSpawn が含まれていないことです。これは、このユーザーアカウントに対して許可されているウィンドウプログラムとして HKEY_CURRENT_USER ます。

詳細については、「許可された Windows アプリケーションのみを実行する」の「[システムポリシー設定への準拠](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)」を参照してください。
