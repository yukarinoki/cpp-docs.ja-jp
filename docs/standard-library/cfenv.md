---
title: '&lt;cfenv&gt;'
ms.date: 11/04/2016
ms.assetid: 6a17ad51-2182-4e91-8108-65997382acd3
ms.openlocfilehash: dcaf49d19009ac831776134cf3d5b6cbce7e14d4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244968"
---
# <a name="ltcfenvgt"></a>&lt;cfenv&gt;

標準 C ライブラリ ヘッダー \<fenv.h> をインクルードし、関連する名前を `std` 名前空間に追加します。

## <a name="syntax"></a>構文

```cpp
#include <cfenv>
```

## <a name="remarks"></a>Remarks

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

## <a name="constants-and-types"></a>定数と型

```cpp
#define FE_ALL_EXCEPT see below
#define FE_DIVBYZERO see below
#define FE_INEXACT see below
#define FE_INVALID see below
#define FE_OVERFLOW see below
#define FE_UNDERFLOW see below
#define FE_DOWNWARD see below
#define FE_TONEAREST see below
#define FE_TOWARDZERO see below
#define FE_UPWARD see below
#define FE_DFL_ENV see below

namespace std {
    using fenv_t = object type ;
    using fexcept_t = integer type ;
}
```

## <a name="functions"></a>関数

```cpp
int feclearexcept(int except);
int fegetexceptflag(fexcept_t* pflag, int except);
int feraiseexcept(int except);
int fesetexceptflag(const fexcept_t* pflag, int except);
int fetestexcept(int except);
int fegetround();
int fesetround(int mode);
int fegetenv(fenv_t* penv);
int feholdexcept(fenv_t* penv);
int fesetenv(const fenv_t* penv);
int feupdateenv(const fenv_t* penv);
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
