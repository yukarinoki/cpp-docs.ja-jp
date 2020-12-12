---
description: '詳細について: CAtlServiceModuleT:: ServiceMain 関数'
title: 'CAtlServiceModuleT:: ServiceMain 関数'
ms.date: 11/04/2016
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 97093d13a2f13ea0d6bd4ba5db46bef45d239cc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148331"
---
# <a name="catlservicemoduletservicemain-function"></a>CAtlServiceModuleT:: ServiceMain 関数

サービスコントロールマネージャー (SCM) は、 `ServiceMain` コントロールパネルの [サービス] アプリケーションを開いてサービスを選択し、[ **開始**] をクリックしたときにを呼び出します。

SCM がを呼び出した後 `ServiceMain` 、サービスは scm にハンドラー関数を与える必要があります。 この関数を使用すると、SCM はサービスの状態を取得し、特定の命令 (一時停止や停止など) を渡すことができます。 SCM は、サービスが `_Handler` Win32 API 関数 [RegisterServiceCtrlHandler](/windows/win32/api/winsvc/nf-winsvc-registerservicectrlhandlerw)に渡すときに、この関数を取得します。 ( `_Handler` は静的でないメンバー関数 [ハンドラー](../atl/reference/catlservicemodulet-class.md#handler)を呼び出す静的メンバー関数です)。

サービスは起動時に、現在の状態を SCM に通知する必要があります。 これを行うには、SERVICE_START_PENDING を Win32 API 関数 [SetServiceStatus](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)に渡します。

`ServiceMain` 次 `CAtlExeModuleT::InitializeCom` に、Win32 API 関数 [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を呼び出すを呼び出します。 既定では、は `InitializeCom` COINIT_MULTITHREADED フラグを関数に渡します。 このフラグは、プログラムがフリースレッドサーバーであることを示します。

ここで、 `CAtlServiceModuleT::Run` は、サービスの主要な作業を実行するために呼び出されます。 `Run` は、サービスが停止するまで実行を続けます。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
