---
title: strict_gs_check |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs:
- C++
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b58b02781f266b24fa321b3849f42b2e090b860
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842977"
---
# <a name="strictgscheck"></a>strict_gs_check
このプラグマは、強化されたセキュリティ チェックを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラが関数スタックにランダム クッキーを挿入し、スタック ベースのバッファー オーバーランのカテゴリの検出に役立つように指示します。 既定では、/GS (バッファー セキュリティ チェック) コンパイラ オプションは、すべての関数に対してクッキーを挿入しません。 詳細については、「[/GS (バッファーのセキュリティ チェック)](../build/reference/gs-buffer-security-check.md)」を参照してください。  
  
 strict_gs_check を有効にするには、/GS (バッファー セキュリティ チェック) でコンパイルする必要があります。  
  
 このプラグマは、有害なデータに対して公開される可能性があるコード モジュールで使用してください。 このプラグマは非常に積極的です。この防御を必要としない可能性があり、ただし生成アプリケーションのパフォーマンスに対する影響を最小化するために最適化された関数に適用されます。  
  
 このプラグマを使用した場合でも、安全なコードを記述する必要があります。 つまり、コードにバッファー オーバーランがないことを確認します。 strict_gs_check は、コードに残っているバッファー オーバーランからアプリケーションを保護する場合があります。  
  
## <a name="example"></a>例  
 次のコードでは、ローカル配列に配列をコピーすると、バッファー オーバーランが発生します。 /GS でこのコードをコンパイルした場合、配列のデータ型はポインターであるため、スタックにクッキーが挿入されません。 strict_gs_check プラグマを追加すると、関数スタックにスタック クッキーを強制します。  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## <a name="see-also"></a>関連項目  
 [プラグマ ディレクティブと _ _pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [/GS (バッファーのセキュリティ チェック)](../build/reference/gs-buffer-security-check.md)