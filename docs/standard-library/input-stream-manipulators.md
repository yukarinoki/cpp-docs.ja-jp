---
title: 入力ストリーム マニピュレーター | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30f642dc4942491bd73265e3d647d3281f97c1e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842206"
---
# <a name="input-stream-manipulators"></a>入力ストリーム マニピュレーター

多くのマニピュレーターなど[setprecision](../standard-library/iomanip-functions.md#setprecision)、用に定義された、`ios`クラス、つまり入力ストリームに適用します。 ただし、入力ストリーム オブジェクトに実際に影響を与えるマニピュレーターはわずかです。 該当するマニピュレーターのうち最も重要なのは、入力ストリームからの数値で使用される変換ベースを決定する基数マニピュレーターの `dec`、`oct`、および `hex` です。

抽出時に、`hex` マニピュレーターでは、さまざまな入力形式を処理できます。 たとえば、c、C、0xc、0xC、0Xc、および 0XC は、すべて 10 進整数の 12 として解釈されます。 0 から 9、A から F、a から f、x、および X 以外の任意の文字によって、数値変換が終了されます。 したがって、シーケンス `"124n5"` は、[basic_ios::fail](../standard-library/basic-ios-class.md#fail) ビットが設定された数値 124 に変換されます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>
