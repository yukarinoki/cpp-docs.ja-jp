---
description: '詳細について: CAtlServiceModuleT:: Start 関数'
title: 'CAtlServiceModuleT:: Start 関数'
ms.date: 11/04/2016
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: cfdae47f88c7957a4470da3129f3d3e071614276
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148318"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT:: Start 関数

サービスが実行されると、は `_tWinMain` `CAtlServiceModuleT::WinMain` を呼び出し、はを呼び出し `CAtlServiceModuleT::Start` ます。

`CAtlServiceModuleT::Start``SERVICE_TABLE_ENTRY`各サービスをスタートアップ関数にマップする構造体の配列を設定します。 この配列は、Win32 API 関数 [startservicectrldispatcher に](/windows/win32/api/winsvc/nf-winsvc-startservicectrldispatcherw)に渡されます。 理論的には、1つの EXE が複数のサービスを処理でき、配列に複数の構造体が含まれる可能性があり `SERVICE_TABLE_ENTRY` ます。 ただし、ATL によって生成されるサービスでは、実行可能ファイルごとに1つのサービスのみがサポートされます。 したがって、配列には、サービス名とスタートアップ関数の1つのエントリがあり `_ServiceMain` ます。 `_ServiceMain` は `CAtlServiceModuleT` 、静的でないメンバー関数を呼び出すの静的メンバー関数です `ServiceMain` 。

> [!NOTE]
> `StartServiceCtrlDispatcher`サービスコントロールマネージャー (SCM) に接続できなかった場合は、プログラムがサービスとして実行されていないことを意味します。 この場合、プログラムは直接を呼び出して、 `CAtlServiceModuleT::Run` プログラムをローカルサーバーとして実行できるようにします。 ローカルサーバーとしてプログラムを実行する方法の詳細については、「 [デバッグのヒント](../atl/debugging-tips.md)」を参照してください。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Start](../atl/reference/catlservicemodulet-class.md#start)
