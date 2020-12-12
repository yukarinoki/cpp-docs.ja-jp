---
description: 詳細については、「入力ストリームマニピュレーター」を参照してください。
title: 入力ストリーム マニピュレーター
ms.date: 11/04/2016
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
ms.openlocfilehash: 3da317a9e01652debe0114cfbde284ec0edf6db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323990"
---
# <a name="input-stream-manipulators"></a>入力ストリーム マニピュレーター

[Setprecision](../standard-library/iomanip-functions.md#setprecision)など、多くのマニピュレーターはクラスに対して定義されているため、 `ios` 入力ストリームに適用されます。 ただし、入力ストリーム オブジェクトに実際に影響を与えるマニピュレーターはわずかです。 該当するマニピュレーターのうち最も重要なのは、入力ストリームからの数値で使用される変換ベースを決定する基数マニピュレーターの `dec`、`oct`、および `hex` です。

抽出時に、`hex` マニピュレーターでは、さまざまな入力形式を処理できます。 たとえば、c、C、0xc、0xC、0Xc、および 0XC は、すべて 10 進整数の 12 として解釈されます。 0 から 9、A から F、a から f、x、および X 以外の任意の文字によって、数値変換が終了されます。 したがって、シーケンス `"124n5"` は、[basic_ios::fail](../standard-library/basic-ios-class.md#fail) ビットが設定された数値 124 に変換されます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)
