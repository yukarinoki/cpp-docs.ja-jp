---
description: 詳細については、ローカルサーバーとしてのプログラムの実行に関するページを参照してください。
title: ローカルサーバーとしてのプログラムの実行
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 1cdf3cef0773769318d68964b28bb60ca66666d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157492"
---
# <a name="running-the-program-as-a-local-server"></a>ローカルサーバーとしてのプログラムの実行

プログラムをサービスとして実行すると不便な場合は、プログラムが通常のローカルサーバーとして実行されるようにレジストリを一時的に変更することができます。 `LocalService`AppID の下の値をに変更し、 `_LocalService` CLSID の下にある `LocalServer32` キーが正しく設定されていることを確認します。 (DCOMCNFG を使用して、アプリケーションを別のコンピューターで実行するように指定すると、キーの名前がに変更されることに注意して `LocalServer32` `_LocalServer32` ください)。ローカルサーバーとしてのプログラムの実行には、起動時に数秒かかり `StartServiceCtrlDispatcher` ます。これは、のの呼び出しが `CAtlServiceModuleT::Start` 失敗するまでに数秒かかるためです。

## <a name="see-also"></a>関連項目

[デバッグのヒント](../atl/debugging-tips.md)
