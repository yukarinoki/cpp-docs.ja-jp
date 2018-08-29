---
title: '現在の時刻: 汎用クラス |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c99a2626c9f60c6407ca9b374bed9c83c981e5b3
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132008"
---
# <a name="current-time-general-purpose-classes"></a>現在の時刻: 汎用クラス
次の手順を作成する方法を示しています、`CTime`オブジェクトし、現在の時刻で初期化します。  
  
#### <a name="to-get-the-current-time"></a>現在の時刻を取得するには  
  
1.  割り当て、`CTime`オブジェクトに、次のようにします。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]  
  
    > [!NOTE]
    >  初期化されていない`CTime`オブジェクトが有効な時刻に初期化されていません。  
  
2.  呼び出す、`CTime::GetCurrentTime`オペレーティング システムから現在の時刻を取得します。 この関数を返します、`CTime`の値を設定するために使用できるオブジェクト`CTime`、次のようにします。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]  
  
     `GetCurrentTime`から静的メンバー関数は、`CTime`クラス、クラスと、スコープ解決演算子の名前、その名前を修飾する必要があります (`::`)、`CTime::GetCurrentTime()`します。  
  
 もちろん、2 つの手順が記載されている以前でした同時に 1 つのプログラム ステートメントとしては、次のように。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]  
  




