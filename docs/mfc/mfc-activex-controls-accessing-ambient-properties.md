---
title: 'MFC ActiveX コントロール : アンビエント プロパティへのアクセス'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
ms.openlocfilehash: e5c78c9943f8baeadcc1198ee8c96f2023ac0215
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625445"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX コントロール : アンビエント プロパティへのアクセス

この記事では、ActiveX コントロールがコントロールコンテナーのアンビエントプロパティにアクセスする方法について説明します。

コントロールは、コンテナーのアンビエントプロパティにアクセスすることによって、コンテナーに関する情報を取得できます。 これらのプロパティは、コンテナーの背景色、コンテナーで使用されている現在のフォント、コンテナーが現在ユーザーモードであるか、またはデザイナーモードであるかなどの操作特性を表示します。 コントロールでは、アンビエントプロパティを使用して、その外観と動作を、埋め込み先の特定のコンテナーに合わせて調整できます。 ただし、コントロールでは、そのコンテナーが特定のアンビエントプロパティをサポートしているとは想定しないでください。 実際、一部のコンテナーではアンビエントプロパティがまったくサポートされない場合があります。 アンビエントプロパティが存在しない場合、コントロールは適切な既定値を想定する必要があります。

アンビエントプロパティにアクセスするには、 [COleControl:: GetAmbientProperty](reference/colecontrol-class.md#getambientproperty)を呼び出します。 この関数は、アンビエントプロパティのディスパッチ ID を最初のパラメーターとして受け取ります (ファイル OLECTL)。H は、アンビエントプロパティの標準セットのディスパッチ Id を定義します。

関数のパラメーターは、 `GetAmbientProperty` ディスパッチ ID、想定されるプロパティの型を示すバリアントタグ、および値が返される必要があるメモリへのポインターです。 このポインターが参照するデータの型は、バリアントタグによって異なります。 この関数は、コンテナーがプロパティをサポートしている場合は**TRUE**を返し、それ以外の場合は**FALSE**を返します。

次のコード例では、"モード" というアンビエントプロパティの値を取得します。 プロパティがコンテナーでサポートされていない場合、既定値の**TRUE**が想定されます。

[!code-cpp[NVC_MFC_AxUI#30](codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

便宜上、には、 `COleControl` 一般的に使用されるアンビエントプロパティの多くにアクセスするヘルパー関数が用意されており、プロパティを使用できない場合には適切な既定値が返されます。 これらのヘルパー関数は次のとおりです。

- [COleControl:: AmbientBackColor](reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  呼び出し元は `Release( )` 、返されたフォントでを呼び出す必要があります。

- [AmbientForeColor](reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](reference/colecontrol-class.md#ambientshowgrabhandles)

アンビエントプロパティの値が (コンテナーの何らかのアクションによって) 変化する `OnAmbientPropertyChanged` と、コントロールのメンバー関数が呼び出されます。 このような通知を処理するには、このメンバー関数をオーバーライドします。 のパラメーター `OnAmbientPropertyChanged` は、影響を受けるアンビエントプロパティのディスパッチ ID です。 このディスパッチ ID の値は DISPID_UNKNOWN である可能性があります。これは、1つまたは複数のアンビエントプロパティが変更されたが、影響を受けたプロパティに関する情報が使用できないことを示します。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
