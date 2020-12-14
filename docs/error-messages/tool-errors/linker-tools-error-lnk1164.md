---
description: 詳細については、「リンカツール Error LNK1164」を参照してください。
title: リンカ ツール エラー LNK1164
ms.date: 11/04/2016
f1_keywords:
- LNK1164
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
ms.openlocfilehash: e4b9b1ae5bb7b15f192869fc8f633abf63cc9507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281146"
---
# <a name="linker-tools-error-lnk1164"></a>リンカ ツール エラー LNK1164

セクションセクションのアラインメント (number) が/ALIGN の値を超えています

オブジェクトファイル内の指定されたセクションのアラインメントサイズが、 [/align](../../build/reference/align-section-alignment.md) オプションで指定された値を超えています。 **/Align** 値は2の累乗でなければなりません。また、オブジェクトファイルで指定されたセクションの配置と同じかそれ以上である必要があります。

セクションの配置を小さくして再コンパイルするか、 **/align** の値を増やしてください。
