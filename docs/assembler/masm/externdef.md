---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 23d34af470e825a8535de8cb28645a7bfb4c4d1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619766"
---
# <a name="externdef"></a>EXTERNDEF

1 つまたは複数の外部変数、ラベル、または記号と呼ばれる定義*名前*型が`type`します。

## <a name="syntax"></a>構文

> EXTERNDEF [langtype] の名前: [、[langtype] の名前: 型の型].

## <a name="remarks"></a>Remarks

場合*名前*が定義されていると見なされます、モジュールで[パブリック](../../assembler/masm/public-masm.md)します。 場合*名前*参照として扱われます、モジュールで[EXTERN](../../assembler/masm/extern-masm.md)。 場合*名前*が参照されていない場合、これは無視されます。 `type`できる[ABS](../../assembler/masm/operator-abs.md)、どの imports*名前*定数として。 通常使用されるインクルード ファイル内で。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>