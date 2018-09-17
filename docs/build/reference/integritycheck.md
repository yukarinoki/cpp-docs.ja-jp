---
title: /INTEGRITYCHECK |Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 062ce019fe1b622661be880d8a06eac9c5971103
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709204"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。

> **/INTEGRITYCHECK****[: NO]**

## <a name="remarks"></a>Remarks

DLL ファイルまたは実行可能ファイルのヘッダーで、このオプションは、Windows でイメージを読み込むために、メモリ マネージャーによるデジタル署名の確認を必要とするフラグを設定します。 Windows Vista 以前の Windows は、このフラグを無視します。 このオプションは、カーネル モード コードを実装する 64 ビット DLL には設定する必要があり、またすべてのデバイス ドライバーに推奨されます。 詳細については、次を参照してください。[カーネル モード コード署名要件](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)します。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)
