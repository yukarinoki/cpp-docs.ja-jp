---
title: オブジェクトの動的生成
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 00e627e6d73e510ca694966291e2ef518fef18b5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619545"
---
# <a name="dynamic-object-creation"></a>オブジェクトの動的生成

この記事では、実行時にオブジェクトを動的に作成する方法について説明します。 このプロシージャは、ランタイム[クラス情報へのアクセス](accessing-run-time-class-information.md)に関する記事で説明されているように、ランタイムクラス情報を使用します。

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>実行時クラスを指定してオブジェクトを動的に作成する

1. の関数を使用してオブジェクトを動的に作成するには、次のコードを使用し `CreateObject` `CRuntimeClass` ます。 失敗した場合、は `CreateObject` 例外を発生させる代わりに**NULL**を返します。

   [!code-cpp[NVC_MFCCObjectSample#6](codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>関連項目

[破棄 (ウィンドウオブジェクト](tn017-destroying-window-objects.md) 
 を)[CObject の使用](using-cobject.md)
