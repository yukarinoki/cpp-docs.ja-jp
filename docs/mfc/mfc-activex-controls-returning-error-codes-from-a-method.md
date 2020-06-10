---
title: 'MFC ActiveX コントロール : メソッドからのエラー コードのリターン'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
ms.openlocfilehash: 1f7564d750b476ac3f57656f3392e0801652e5d5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615518"
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>MFC ActiveX コントロール : メソッドからのエラー コードのリターン

この記事では、ActiveX コントロールメソッドからエラーコードを返す方法について説明します。

メソッド内でエラーが発生したことを示すには、パラメーターとして SCODE (状態コード) を受け取る、 [COleControl:: ThrowError](reference/colecontrol-class.md#throwerror)メンバー関数を使用する必要があります。 定義済みの SCODE を使用することも、独自の SCODE を定義することもできます。

> [!NOTE]
> `ThrowError`は、プロパティの Get または Set 関数またはオートメーションメソッド内からエラーを返す手段としてのみ使用されることを意図しています。 これらは、適切な例外ハンドラーがスタックに存在する唯一の時間です。

このヘルパー関数は、最も一般的な定義済みの SCODEs (例: [colecontrol:: SetNotSupported](reference/colecontrol-class.md#setnotsupported)、 [Colecontrol:: GetNotSupported](reference/colecontrol-class.md#getnotsupported)、および[colecontrol:: setnotpermitted](reference/colecontrol-class.md#setnotpermitted)) に対して存在します。

定義済みの SCODEs の一覧およびカスタム SCODEs を定義する手順については、「ActiveX コントロールでの[エラーの処理](mfc-activex-controls-advanced-topics.md): 高度なトピック」を参照してください。

コードの他の領域の例外を報告する方法の詳細については、「 [COleControl:: 焼討 error](reference/colecontrol-class.md#fireerror) 」と「activex コントロールの[activex コントロールでのエラー処理](mfc-activex-controls-advanced-topics.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
