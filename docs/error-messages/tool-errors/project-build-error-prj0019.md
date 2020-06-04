---
title: プロジェクト ビルド エラー PRJ0019
ms.date: 11/04/2016
f1_keywords:
- PRJ0019
helpviewer_keywords:
- PRJ0019
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
ms.openlocfilehash: 3aed7ca5dcf5803305d8765f50430520a5b73d2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80192537"
---
# <a name="project-build-error-prj0019"></a>プロジェクト ビルド エラー PRJ0019

ツールからエラーコードが返されました

カスタムビルドステップまたはビルドイベントでは、エラーレベルは0以外でした。

また、ツールがエラーコードを返してもエラーメッセージが返されなかった場合にも、PRJ0019 が表示されます。 これは、たとえば、MIDL の出力を NUL にリダイレクトする場合に発生する可能性があります。

詳細については[、「カスタムビルドステップのトラブルシューティング」および「ビルドイベント](../../build/troubleshooting-build-customizations.md)」を参照してください。

このエラーは、ユーザーグループのメンバとしてを実行していて、管理アクセスが必要な場合にも発生することがあります。 詳細については、「 [Users グループのメンバーとし](../../security/running-as-a-member-of-the-users-group.md)ての実行」を参照してください。
