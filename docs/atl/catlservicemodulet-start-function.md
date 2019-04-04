---
title: Catlservicemodulet::start 関数
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 204d02a1122ee78b38850bedae5f98b1f338ab1d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816283"
---
# <a name="catlservicemoduletstart-function"></a>Catlservicemodulet::start 関数

サービスが実行される`_tWinMain`呼び出し`CAtlServiceModuleT::WinMain`、この`CAtlServiceModuleT::Start`します。

`CAtlServiceModuleT::Start` 配列を設定`SERVICE_TABLE_ENTRY`各サービスをそのスタートアップ関数にマップする構造体。 この配列は、Win32 API 関数に渡されます[StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera)します。 1 つの EXE は理論上は、複数のサービスを処理する可能性がありますあり、配列が複数`SERVICE_TABLE_ENTRY`構造体。 現時点では、ただし、ATL によって生成されたサービスがサポートする実行可能ファイルごとにサービスを 1 つだけです。 したがって、配列にはサービス名を含む 1 つのエントリと`_ServiceMain`としてスタートアップ関数。 `_ServiceMain` 静的メンバー関数は、 `CAtlServiceModuleT` 、非静的メンバー関数を呼び出す`ServiceMain`します。

> [!NOTE]
>  エラー`StartServiceCtrlDispatcher`をサービス コントロールへの接続マネージャー (SCM) はほとんど意味をサービスとして、プログラムが実行されていないこと。 この場合、呼び出しプログラム`CAtlServiceModuleT::Run`直接プログラムは、ローカル サーバーとして実行できるようにします。 詳細については、ローカル サーバーとしてプログラムを実行して、[デバッグのヒント](../atl/debugging-tips.md)を参照してください。

## <a name="see-also"></a>関連項目

[Services](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)
