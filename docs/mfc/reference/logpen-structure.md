---
title: LOGPEN 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a535858a0d5540db481fd42918b4079f30c90728
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375674"
---
# <a name="logpen-structure"></a>LOGPEN 構造体

`LOGPEN`構造体、スタイル、幅、およびペンの色の定義、描画するために使用される描画オブジェクトの直線し境界線します。 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)関数は、`LOGPEN`構造体。

## <a name="syntax"></a>構文

```
typedef struct tagLOGPEN {  /* lgpn */
    UINT lopnStyle;
    POINT lopnWidth;
    COLORREF lopnColor;
} LOGPEN;
```

#### <a name="parameters"></a>パラメーター

*lopnStyle*<br/>
ペンの種類を指定します。 このメンバーには、次の値のいずれかを指定できます。

- きは、solid ペンを作成します。

- PS_DASH は破線のペンを作成します。 (ペンの幅が 1 の場合にのみ有効です。)

- PS_DOT 点線のペンを作成します。 (ペンの幅が 1 の場合にのみ有効です。)

- 交互に使用するペン ダッシュし、ドット PS_DASHDOT を作成します。 (ペンの幅が 1 の場合にのみ有効です。)

- PS_DASHDOTDOT を代替ダッシュと 2 つのドットを使用するペンを作成します。 (ペンの幅が 1 の場合にのみ有効です。)

- 必ずでは、null のペンを作成します。

- 出力の外接する四角形を指定する関数をペンで閉じた図形のフレーム内の行を描画するペンの生成を作成、GDI (たとえば、 `Ellipse`、 `Rectangle`、 `RoundRect`、 `Pie`、および`Chord`メンバー関数の場合)。 外接する四角形が指定されていない関数の出力 GDI を使用してこのスタイルを使用する場合 (たとえば、`LineTo`メンバー関数)、枠は、ペンの描画領域に制限されません。

     ペンにペン スタイルと色が論理カラー テーブルで使用する色に一致しない場合、ペンをディザリングされた色で描画します。 ディザリングされた色でペンを作成するきはペンのスタイルを使用できません。 ペンの幅が 1 に等しいまたはそれよりも小さい場合は、ペンのスタイルをきと同じです。

     以外の関数によって生成された GDI オブジェクトでペンのスタイルを使用するときに`Ellipse`、 `Rectangle`、および`RoundRect`、行できない可能性があります完全に指定したフレーム内で。

*lopnWidth*<br/>
論理ユニットでは、ペンの幅を指定します。 場合、`lopnWidth`メンバーが 0 のペンは現在のマッピング モードに関係なくラスター デバイス上の 1 ピクセル場合、です。

*lopnColor*<br/>
ペンの色を指定します。

## <a name="remarks"></a>Remarks

`y`値、[ポイント](../../mfc/reference/point-structure1.md)用の構造、`lopnWidth`メンバーは使用されません。

## <a name="requirements"></a>要件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

