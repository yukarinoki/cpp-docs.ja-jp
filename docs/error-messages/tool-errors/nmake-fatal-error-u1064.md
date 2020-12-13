---
description: 詳細については、「NMAKE の致命的なエラー U1064」を参照してください。
title: NMAKE の致命的なエラー U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: 881c93eca4efad064dff633bbde34dc88e71345e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330363"
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE の致命的なエラー U1064

メイクファイルが見つからず、ターゲットが指定されていません

NMAKE コマンドラインで、メイクファイルまたはターゲットが指定されませんでした。現在のディレクトリには、MAKEFILE という名前のファイルが含まれていませんでした。

NMAKE には、メイクファイルまたはコマンドラインターゲット (またはその両方) が必要です。 メイクファイルを NMAKE で使用できるようにするには、/F オプションを指定するか、または MAKEFILE という名前のファイルを現在のディレクトリに配置します。 メイクファイルが指定されていない場合、NMAKE は推論規則を使用してコマンドラインターゲットを作成できます。
