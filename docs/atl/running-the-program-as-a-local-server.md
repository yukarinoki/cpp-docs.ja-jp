---
title: ローカル サーバーとして、プログラムの実行 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7ff7c2f7564a5da2c7a1db3913526a95660fe1d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754684"
---
# <a name="running-the-program-as-a-local-server"></a>ローカル サーバーとしてプログラムを実行します。

サービスとしてプログラムを実行する便利な場合、プログラムが通常のローカル サーバーとして実行されるように、レジストリを一時的に変更することができます。 変更するだけ、`LocalService`下に、AppID 値`_LocalService`を確認してください、 `LocalServer32` CLSID でキーが正しく設定します。 (こと DCOMCNFG を使用して、別のコンピューターでアプリケーションを実行することを指定する名前を変更に注意してください、`LocalServer32`キー `_LocalServer32`)。プログラムを実行しているために、ローカル サーバーが起動時にあと数秒を受け取るよう呼び出し`StartServiceCtrlDispatcher`で`CAtlServiceModuleT::Start`それが失敗するまで数秒かかります。

## <a name="see-also"></a>関連項目

[デバッグのヒント](../atl/debugging-tips.md)

