---
title: 現在の時刻:汎用クラス
ms.date: 11/04/2016
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
ms.openlocfilehash: e883a47243feb7ad1555748ffdda9b8ae9594644
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62236215"
---
# <a name="current-time-general-purpose-classes"></a>現在の時刻:汎用クラス

次の手順を作成する方法を示しています、`CTime`オブジェクトし、現在の時刻で初期化します。

### <a name="to-get-the-current-time"></a>現在の時刻を取得するには

1. 割り当て、`CTime`オブジェクトに、次のようにします。

   [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]

   > [!NOTE]
   > 初期化されていない`CTime`オブジェクトが有効な時刻に初期化されていません。

1. 呼び出す、`CTime::GetCurrentTime`オペレーティング システムから現在の時刻を取得します。 この関数を返します、`CTime`の値を設定するために使用できるオブジェクト`CTime`、次のようにします。

   [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]

   `GetCurrentTime`から静的メンバー関数は、`CTime`クラス、クラスと、スコープ解決演算子の名前、その名前を修飾する必要があります (`::`)、`CTime::GetCurrentTime()`します。

もちろん、2 つの手順が記載されている以前でした同時に 1 つのプログラム ステートメントとしては、次のように。

[!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]
