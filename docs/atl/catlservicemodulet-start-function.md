---
title: Catlservicemodulet::start 関数
ms.date: 11/04/2016
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 0730bad600190ed06c6f40a4a7cf396f0924a5fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476635"
---
# <a name="catlservicemoduletstart-function"></a>Catlservicemodulet::start 関数

サービスが実行される`_tWinMain`呼び出し`CAtlServiceModuleT::WinMain`、この`CAtlServiceModuleT::Start`します。

`CAtlServiceModuleT::Start` 配列を設定`SERVICE_TABLE_ENTRY`各サービスをそのスタートアップ関数にマップする構造体。 この配列は、Win32 API 関数に渡されます[StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera)します。 1 つの EXE は理論上は、複数のサービスを処理する可能性がありますあり、配列が複数`SERVICE_TABLE_ENTRY`構造体。 現時点では、ただし、ATL によって生成されたサービスがサポートする実行可能ファイルごとにサービスを 1 つだけです。 したがって、配列にはサービス名を含む 1 つのエントリと`_ServiceMain`としてスタートアップ関数。 `_ServiceMain` 静的メンバー関数は、 `CAtlServiceModuleT` 、非静的メンバー関数を呼び出す`ServiceMain`します。

> [!NOTE]
>  エラー`StartServiceCtrlDispatcher`をサービス コントロールへの接続マネージャー (SCM) はほとんど意味をサービスとして、プログラムが実行されていないこと。 この場合、呼び出しプログラム`CAtlServiceModuleT::Run`直接プログラムは、ローカル サーバーとして実行できるようにします。 詳細については、ローカル サーバーとしてプログラムを実行して、次を参照してください。[デバッグのヒント](../atl/debugging-tips.md)します。

## <a name="see-also"></a>関連項目

[Services](../atl/atl-services.md)<br/>
[Catlservicemodulet::start](../atl/reference/catlservicemodulet-class.md#start)

