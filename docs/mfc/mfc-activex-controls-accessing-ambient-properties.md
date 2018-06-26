---
title: 'MFC ActiveX コントロール: アンビエント プロパティにアクセスする |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd3376e19d7780922102240ae1bfaa1b4eb89b2b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931724"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX コントロール : アンビエント プロパティへのアクセス
この記事では、ActiveX コントロールがそのコントロールのコンテナーのアンビエント プロパティにアクセスする方法について説明します。  
  
 コントロールは、コンテナーのアンビエント プロパティにアクセスして、コンテナーに関する情報を取得できます。 これらのプロパティは、コンテナーの背景色、かどうか、コンテナーは、現在ユーザー モードまたはデザイナー モードでは、コンテナー、および運用上の特性で使用される現在のフォントなどのビジュアルの特性を公開します。 コントロールは、アンビエント プロパティを使用して、、外観や動作に埋め込まれている特定のコンテナーを調整できます。 ただし、コントロールでは、そのコンテナーですべてのアンビエント プロパティをサポートする必要があります考えないでください。 実際には、一部のコンテナーでは、アンビエント プロパティがまったくサポートいない可能性があります。 アンビエント プロパティがない場合、コントロールが適切な既定値を想定してください。  
  
 アンビエント プロパティにアクセスするには、呼び出しを行う[COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty)です。 この関数は、(ファイルとして使用最初のパラメーターとしてアンビエント プロパティのディスパッチ ID が必要でします。H 定義アンビエント プロパティの一連の標準のディスパッチ Id)。  
  
 パラメーター、`GetAmbientProperty`関数は、ディスパッチ ID、予期されたプロパティの型、およびメモリへのポインターを示すバリアント型のタグ値を返す必要があります。 このポインターが参照するデータの種類は、バリアント型のタグによって異なります。 この関数を返します**TRUE**コンテナーは、プロパティをサポートする場合を返します**FALSE**です。  
  
 次のコード例は、"UserMode"と呼ばれるアンビエント プロパティの値を取得します。 プロパティは、既定値は、コンテナーによってサポートされていませんかどうか**TRUE**と見なされます。  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 必要に応じて、`COleControl`多くの一般的に使用されるアンビエント プロパティにアクセスし、プロパティは利用できない場合は、適切な既定値を返すヘルパー関数を提供します。 これらのヘルパー関数は次のとおりです。  
  
-   [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)  
  
-   [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)  
  
-   [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)  
  
    > [!NOTE]
    >  呼び出し元が呼び出す必要があります`Release( )`返されたフォントです。  
  
-   [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)  
  
-   [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)  
  
-   [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)  
  
-   [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)  
  
-   [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)  
  
-   [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)  
  
-   [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)  
  
-   [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)  
  
 (一部の操作によって、コンテナーの)、アンビエント プロパティの値が変更された場合、`OnAmbientPropertyChanged`コントロールのメンバー関数が呼び出されます。 このような通知を処理するには、このメンバー関数をオーバーライドします。 パラメーターを`OnAmbientPropertyChanged`影響を受けるアンビエント プロパティのディスパッチ id を指定します。 このディスパッチ ID の値の 1 つまたは複数のアンビエント プロパティが変更されたことを示す、DISPID_UNKNOWN 可能性がありますが、影響を受けたプロパティに関する情報が利用できません。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

