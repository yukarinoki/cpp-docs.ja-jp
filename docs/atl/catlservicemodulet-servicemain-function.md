---
title: Catlservicemodulet::servicemain 関数
ms.date: 11/04/2016
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
helpviewer_keywords:
- ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
ms.openlocfilehash: 32bdea1eb39c91ddb58def72bd16acc2f16ab936
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295423"
---
# <a name="catlservicemoduletservicemain-function"></a>Catlservicemodulet::servicemain 関数

サービス コントロール マネージャー (SCM) を呼び出す`ServiceMain`コントロール パネルの サービス アプリケーションを開くと、サービスを選択し、をクリックして**開始**します。

SCM の後に呼び出す`ServiceMain`サービスがハンドラー関数には、SCM の付ける必要があります。 この関数では、SCM はサービスの状態を取得して (一時停止、停止など) の具体的な手順を渡すことができます。 SCM がサービスを通過するとき、この関数を取得`_Handler`、Win32 API 関数に[RegisterServiceCtrlHandler](/windows/desktop/api/winsvc/nf-winsvc-registerservicectrlhandlera)します。 (`_Handler`非静的メンバー関数を呼び出す静的メンバー関数は、[ハンドラー](../atl/reference/catlservicemodulet-class.md#handler))。

起動時に、サービスは、現在の状態の SCM も知らせる必要があります。 これは、Win32 API 関数に SERVICE_START_PENDING を渡すことによって、 [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)します。

`ServiceMain` 呼び出して`CAtlExeModuleT::InitializeCom`、Win32 API 関数を呼び出し[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex)します。 既定では、 `InitializeCom` COINIT_MULTITHREADED フラグを関数に渡します。 このフラグは、プログラムがフリー スレッド サーバーであることを示します。

ここで、`CAtlServiceModuleT::Run`サービスの主な作業を実行すると呼びます。 `Run` サービスが停止するまで実行を継続します。

## <a name="see-also"></a>関連項目

[Services](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)
