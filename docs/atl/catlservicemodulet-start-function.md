---
title: 関数の開始
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 50054bbb34bcc31a1d11dd8bfab797f98e4e82f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317276"
---
# <a name="catlservicemoduletstart-function"></a>関数の開始

サービスが実行されると、`_tWinMain`が`CAtlServiceModuleT::WinMain`呼び出され、`CAtlServiceModuleT::Start`が呼び出されます。

`CAtlServiceModuleT::Start`では、各サービスを`SERVICE_TABLE_ENTRY`起動関数にマップする構造体の配列を設定します。 この配列は、Win32 API 関数の[開始サービスCtrlディスパッチャーに渡されます](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)。 理論的には、1つのEXEが複数のサービスを処理することができ、配列`SERVICE_TABLE_ENTRY`は複数の構造を持つことができます。 しかし、現在、ATL によって生成されたサービスは、EXE ごとに 1 つのサービスのみをサポートしています。 したがって、この配列には、サービス名と`_ServiceMain`スタートアップ関数を含む単一のエントリがあります。 `_ServiceMain`は、非静的メンバー関数`CAtlServiceModuleT`を呼び出す静的メンバー関数です`ServiceMain`。

> [!NOTE]
> `StartServiceCtrlDispatcher`サービス コントロール マネージャー (SCM) に接続できない場合は、プログラムがサービスとして実行されていない可能性があります。 この場合、プログラムは直接呼`CAtlServiceModuleT::Run`び出して、プログラムをローカル サーバーとして実行できるようにします。 プログラムをローカル サーバーとして実行する方法の詳細については、「[デバッグのヒント](../atl/debugging-tips.md)」を参照してください。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[開始](../atl/reference/catlservicemodulet-class.md#start)
