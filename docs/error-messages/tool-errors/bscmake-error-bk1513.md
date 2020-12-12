---
description: 詳細については、「BSCMAKE エラー BK1513」を参照してください。
title: BSCMAKE エラー BK1513
ms.date: 11/04/2016
f1_keywords:
- BK1513
helpviewer_keywords:
- BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
ms.openlocfilehash: bdf26e3268f98e5ab41ef27bbeaa3734a001671a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238090"
---
# <a name="bscmake-error-bk1513"></a>BSCMAKE エラー BK1513

インクリメンタルでないビルドにはすべての .SBR ファイルが必要です。

1 つ以上の .sbr ファイルが切り捨てられたため、BSCMAKE では、新しいブラウザー情報 (.bsc) ファイルをビルドできません。 切り捨てられた .sbr ファイルの名前を確認するには、このエラーに付随する [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) の警告を参照してください。

BSCMAKE では .bsc ファイルを切り捨てられた .sbr ファイルで更新できますが、新しいものをビルドすることはできません。 BSCMAKE では、次の理由で新しい .bsc ファイルをビルドする可能性があります。

- .bsc ファイルが欠落しています。

- .bsc ファイルに指定されたファイル名が間違っています。

- .bsc ファイルが破損しています。

この問題を解決するには、切り捨てられた .sbr ファイルを削除して再ビルドするか、または、ソリューションをクリーンして再ビルドします。 (IDE で、[ **ビルド**]、[ **ソリューションのクリーン**] の順に選択し、[ **ビルド**]、[ **ソリューションのリビルド**] の順に選択します)。
