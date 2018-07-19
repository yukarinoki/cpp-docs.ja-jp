---
title: system_error クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- system_error/std::system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bde8e448d54be41516e65969f60b0651cacc8ef1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854559"
---
# <a name="systemerror-class"></a>system_error クラス

低レベル システムエラーをレポートするためにスローされるすべての例外のための基底クラスを表します。

## <a name="syntax"></a>構文

```cpp
class system_error : public runtime_error {
public:
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

};
```

## <a name="remarks"></a>コメント

クラス [exception](../standard-library/exception-class.md) で `what` によって返される値は、`_Message` および型 [error_code](../standard-library/error-code-class.md) (`code` または `error_code(_Errval, _Errcat)` のいずれか) の格納されているオブジェクトから構築されます。

メンバー関数 `code` は、格納されている [error_code](../standard-library/error-code-class.md) オブジェクトを返します。

## <a name="requirements"></a>要件

**ヘッダー:** \<system_error>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<system_error>](../standard-library/system-error.md)<br/>
