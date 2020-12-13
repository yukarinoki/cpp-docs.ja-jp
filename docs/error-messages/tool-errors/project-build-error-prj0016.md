---
description: 詳細については、「プロジェクトビルドエラー PRJ0016」を参照してください。
title: プロジェクト ビルド エラー PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: a34783e46bbe4c7b9979fe9b3d200cde4c228885
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343835"
---
# <a name="project-build-error-prj0016"></a>プロジェクト ビルド エラー PRJ0016

ユーザーのセキュリティ設定により、プロセスを作成できません。 これらの設定は、ビルドに必要です。

プロセスを使用してプロセスを作成するアクセス許可を持たないユーザーとしてログインしています。 このユーザーアカウントのアクセス許可レベルを変更するか、アカウント管理者に連絡してください。

このエラーは、次のレジストリキーが設定されている場合にも発生する可能性があります。

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

このエラーを解決するには、RestrictRun キーを削除します。 このレジストリキーが必要な場合は、キーのエントリの一覧に **vcspawn.exe** を追加します。

このエラーの別の原因として、ポリシー設定には、このユーザーアカウントで許可されているウィンドウプログラムとして HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun レジストリキーの下に VCSpawn.exe が含まれていないことが挙げられます。

詳細については、「許可された Windows アプリケーションのみを実行する」の「 [システムポリシー設定への準拠](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)」を参照してください。
