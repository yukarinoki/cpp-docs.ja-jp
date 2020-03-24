---
title: リンカ ツール エラー LNK1164
ms.date: 11/04/2016
f1_keywords:
- LNK1164
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
ms.openlocfilehash: 5f32fbd455faff449f57cfb9bb38009b03005913
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184035"
---
# <a name="linker-tools-error-lnk1164"></a>リンカ ツール エラー LNK1164

セクションセクションのアラインメント (number) が/ALIGN の値を超えています

オブジェクトファイル内の指定されたセクションのアラインメントサイズが、 [/align](../../build/reference/align-section-alignment.md)オプションで指定された値を超えています。 **/Align**値は2の累乗でなければなりません。また、オブジェクトファイルで指定されたセクションの配置と同じかそれ以上である必要があります。

セクションの配置を小さくして再コンパイルするか、 **/align**の値を増やしてください。
