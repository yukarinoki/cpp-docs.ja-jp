---
title: 集計およびクラスファクトリマクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
ms.openlocfilehash: 554210ab0a26bc54a716a389a1660c4cbd42a209
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168658"
---
# <a name="aggregation-and-class-factory-macros"></a>集計およびクラスファクトリマクロ

これらのマクロは、集計を制御し、クラスファクトリを宣言する方法を提供します。

|||
|-|-|
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|オブジェクトを集計できる (既定値) ことを宣言します。|
|[DECLARE_CLASSFACTORY](#declare_classfactory)|ATL の既定のクラスファクトリである[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)するクラスファクトリを宣言します。|
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|クラスファクトリオブジェクトをクラスファクトリとして宣言します。|
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)をクラスファクトリとして宣言します。|
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)をクラスファクトリとして宣言します。|
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)をクラスファクトリとして宣言します。|
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|仮想`GetControllingUnknown`関数を宣言します。|
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|オブジェクトを集計できないことを宣言します。|
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|オブジェクトを集計する必要があることを宣言します。|
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|外側の不明の値を確認し、必要に応じて、オブジェクトを集計可能または集計不可能として宣言します。|
|[DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|内部オブジェクトの構築時に外部オブジェクトが削除されないように保護します。|
|[DECLARE_VIEW_STATUS](#declare_view_status)|コンテナーに VIEWSTATUS フラグを指定します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="declare_aggregatable"></a><a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE

オブジェクトを集計できることを指定します。

```cpp
DECLARE_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
から集計可能として定義するクラスの名前。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定の集計モデルを指定するこのマクロが含まれています。 この既定値をオーバーライドするには、クラス定義で[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)または[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)マクロを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_classfactory"></a><a name="declare_classfactory"></a>DECLARE_CLASSFACTORY

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)をクラスファクトリとして宣言します。

```cpp
DECLARE_CLASSFACTORY()
```

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)は、このマクロを使用して、オブジェクトの既定のクラスファクトリを宣言します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]

## <a name="ccomclassfactory-class"></a><a name="ccomclassfactory_class"></a>CComClassFactory クラス

このクラスは、 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。

```cpp
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>解説

`CComClassFactory`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装します。このインターフェイスには、特定の CLSID のオブジェクトを作成するためのメソッドが含まれています。また、新しいオブジェクトをより迅速に作成できるように、メモリ内のクラスファクトリをロックすることもできます。 `IClassFactory`は、システムレジストリに登録し、CLSID を割り当てるすべてのクラスに対して実装する必要があります。

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [DECLARE_CLASSFACTORY](#declare_classfactory)既定のクラスファクトリ`CComClassFactory`として宣言するマクロ DECLARE_CLASSFACTORY が含まれています。 この既定値をオーバーライドするには、クラス定義で DECLARE_CLASSFACTORY*XXX*マクロのいずれかを指定します。 たとえば、 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)マクロはクラスファクトリに対して指定されたクラスを使用します。

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

上のクラス定義では`CMyClassFactory` 、がオブジェクトの既定のクラスファクトリとして使用されることを指定しています。 `CMyClassFactory`はから`CComClassFactory`派生し、 `CreateInstance`をオーバーライドする必要があります。

ATL には、クラスファクトリを宣言する次の3つのマクロが用意されています。

- [DECLARE_CLASSFACTORY2](#declare_classfactory2)[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)を使用します。これはライセンスによる作成を制御します。

- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)複数のアパートメントにオブジェクトを作成する[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)を使用します。

- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)1つの[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクトを構築する[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を使用します。

## <a name="declare_classfactory_ex"></a><a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX

を`cf`クラスファクトリとして宣言します。

```cpp
DECLARE_CLASSFACTORY_EX( cf )
```

### <a name="parameters"></a>パラメーター

*cf*<br/>
からクラスファクトリオブジェクトを実装するクラスの名前。

### <a name="remarks"></a>解説

*Cf*パラメーターは[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)から派生し、メソッドを`CreateInstance`オーバーライドする必要があります。

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には[DECLARE_CLASSFACTORY](#declare_classfactory) 、既定のクラスファクトリ`CComClassFactory`としてを指定する DECLARE_CLASSFACTORY マクロが含まれています。 ただし、オブジェクトのクラス定義に DECLARE_CLASSFACTORY_EX マクロを含めることにより、この既定値をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]

## <a name="declare_classfactory2"></a><a name="declare_classfactory2"></a>DECLARE_CLASSFACTORY2

[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)をクラスファクトリとして宣言します。

```cpp
DECLARE_CLASSFACTORY2( lic )
```

### <a name="parameters"></a>パラメーター

*lic*<br/>
から、 `GetLicenseKey`、および`IsLicenseValid`を`VerifyLicenseKey`実装するクラス。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラスファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義に DECLARE_CLASSFACTORY2 マクロを含めることにより、この既定値をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

## <a name="ccomclassfactory2-class"></a><a name="ccomclassfactory2_class"></a>CComClassFactory2 クラス

このクラスは、 [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスを実装します。

```cpp
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

### <a name="parameters"></a>パラメーター

*使用*<br/>
次の静的関数を実装するクラス。

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

### <a name="remarks"></a>解説

`CComClassFactory2`[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)の拡張である[IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)インターフェイスを実装します。 `IClassFactory2`ライセンスによってオブジェクトの作成を制御します。 ライセンスされたコンピューターで実行されるクラスファクトリは、実行時ライセンスキーを提供できます。 このライセンスキーを使用すると、アプリケーションは、完全なコンピューターライセンスが存在しない場合にオブジェクトをインスタンス化できます。

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラスファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](#declare_classfactory)が含まれています。 を使用`CComClassFactory2`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY2](#declare_classfactory2)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]

`CMyLicense`の`CComClassFactory2`テンプレートパラメーターは、静的`VerifyLicenseKey`関数、 `GetLicenseKey`、および`IsLicenseValid`を実装する必要があります。 単純なライセンスクラスの例を次に示します。

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]

`CComClassFactory2`との両方`CComClassFactory2Base`の*ライセンス*から派生します。 `CComClassFactory2Base`さらに、はから派生`IClassFactory2`し **、\< CComObjectRootEx CComGlobalsThreadModel >** から派生します。

## <a name="declare_classfactory_auto_thread"></a><a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD

[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)をクラスファクトリとして宣言します。

```cpp
DECLARE_CLASSFACTORY_AUTO_THREAD()
```

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラスファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義に DECLARE_CLASSFACTORY_AUTO_THREAD マクロを含めることにより、この既定値をオーバーライドします。

(アウトプロセスサーバーで) 複数のアパートメントにオブジェクトを作成する場合は、クラスに DECLARE_CLASSFACTORY_AUTO_THREAD を追加します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="ccomclassfactoryautothread-class"></a><a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread クラス

このクラスは、 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)インターフェイスを実装し、複数のアパートメントでオブジェクトを作成できるようにします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

```cpp
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```

### <a name="remarks"></a>解説

`CComClassFactoryAutoThread`は[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)に似ていますが、複数のアパートメントでオブジェクトを作成することができます。 このサポートを利用するには、 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)から EXE モジュールを派生させます。

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を既定のクラスファクトリとして宣言するマクロ[DECLARE_CLASSFACTORY](#declare_classfactory)が含まれています。 を使用`CComClassFactoryAutoThread`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]

## <a name="declare_classfactory_singleton"></a><a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON

[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)をクラスファクトリとして宣言します。

```cpp
DECLARE_CLASSFACTORY_SINGLETON( obj )
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
からクラスオブジェクトの名前。

### <a name="remarks"></a>解説

[CComCoClass](../../atl/reference/ccomcoclass-class.md)には、既定のクラスファクトリとして[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を指定する[DECLARE_CLASSFACTORY](#declare_classfactory)マクロが含まれています。 ただし、オブジェクトのクラス定義に DECLARE_CLASSFACTORY_SINGLETON マクロを含めることにより、この既定値をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="ccomclassfactorysingleton-class"></a><a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton クラス

このクラスは、 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)から派生し、 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用して1つのオブジェクトを構築します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

```cpp
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス。

`CComClassFactorySingleton`[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)から派生し、 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を使用して1つのオブジェクトを構築します。 メソッドを呼び出す`CreateInstance`たびに、このオブジェクトに対してインターフェイスポインターがクエリされます。

### <a name="remarks"></a>解説

ATL オブジェクトは通常、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)から派生することによってクラスファクトリを取得します。 このクラスには、 [DECLARE_CLASSFACTORY](#declare_classfactory)既定のクラスファクトリ`CComClassFactory`として宣言するマクロ DECLARE_CLASSFACTORY が含まれています。 を使用`CComClassFactorySingleton`するには、オブジェクトのクラス定義で[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)マクロを指定します。 次に例を示します。

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]

## <a name="declare_get_controlling_unknown"></a><a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN

仮想関数`GetControllingUnknown`を宣言します。

```cpp
DECLARE_GET_CONTROLLING_UNKNOWN()
```

### <a name="remarks"></a>解説

未定義のコンパイラエラーメッセージが表示される`GetControllingUnknown`場合は、このマクロをオブジェクトに追加します ( `CComAggregateCreator`たとえば、)。

## <a name="declare_not_aggregatable"></a><a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE

オブジェクトを集計できないことを指定します。

```cpp
DECLARE_NOT_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
から集計可能ではないとして定義するクラスオブジェクトの名前。

### <a name="remarks"></a>解説

オブジェクトに`CreateInstance`対して集計を行おうとすると、DECLARE_NOT_AGGREGATABLE によってエラー (CLASS_E_NOAGGREGATION) が返されます。

既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)には、オブジェクトを集約できることを指定する[DECLARE_AGGREGATABLE](#declare_aggregatable)マクロが含まれています。 この既定の動作をオーバーライドするには、クラス定義に DECLARE_NOT_AGGREGATABLE を含めます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]

## <a name="declare_only_aggregatable"></a><a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE

オブジェクトを集計する必要があることを指定します。

```cpp
DECLARE_ONLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
から集計可能なものとして定義するクラスオブジェクトの名前。

### <a name="remarks"></a>解説

オブジェクトが非集計オブジェクトとして試行された場合、 `CoCreate` DECLARE_ONLY_AGGREGATABLE によってエラー (E_FAIL) が発生します。

既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)には、オブジェクトを集約できることを指定する[DECLARE_AGGREGATABLE](#declare_aggregatable)マクロが含まれています。 この既定の動作をオーバーライドするには、クラス定義に DECLARE_ONLY_AGGREGATABLE を含めます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]

## <a name="declare_poly_aggregatable"></a><a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE

オブジェクトの作成時に**CComPolyObject \< ** *x* **>** のインスタンスを作成することを指定します。

```cpp
DECLARE_POLY_AGGREGATABLE( x )
```

### <a name="parameters"></a>パラメーター

*x*<br/>
から集計可能または集計不可能として定義するクラスオブジェクトの名前。

### <a name="remarks"></a>解説

作成時に、[外側の不明] の値がチェックされます。 NULL の場合は、 `IUnknown`非集計オブジェクトに対してが実装されます。 外側の unknown が NULL でない場合`IUnknown` 、は集計オブジェクトに対して実装されます。

DECLARE_POLY_AGGREGATABLE を使用する利点は、集計された`CComAggObject`ケース`CComObject`と非集計ケースを処理するためにとの両方のモジュールを使用しないことです。 1つ`CComPolyObject`のオブジェクトが両方のケースを処理します。 つまり、モジュールには vtable のコピーと関数のコピーが1つだけ存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に減らすことができます。 ただし、vtable が小さい場合、を使用`CComPolyObject`する`CComAggObject`と、と`CComObject`のように集計または非集計オブジェクトに対して最適化されていないため、モジュールサイズが少し大きくなります。

ATL コントロールウィザードを使用してフルコントロールを作成すると、オブジェクト内で DECLARE_POLY_AGGREGATABLE マクロが自動的に宣言されます。

## <a name="declare_protect_final_construct"></a><a name="declare_protect_final_construct"></a>DECLARE_PROTECT_FINAL_CONSTRUCT

( [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)中に) 内部集計オブジェクトが参照カウントをインクリメントし、カウントを0にデクリメントする場合に、オブジェクトが削除されないように保護します。

```cpp
DECLARE_PROTECT_FINAL_CONSTRUCT()
```

## <a name="declare_view_status"></a><a name="declare_view_status"></a>DECLARE_VIEW_STATUS

このマクロを ATL ActiveX コントロールのコントロールクラスに配置して、VIEWSTATUS フラグをコンテナーに指定します。

```cpp
DECLARE_VIEW_STATUS( statusFlags )
```

### <a name="parameters"></a>パラメーター

*statusFlags*<br/>
からVIEWSTATUS フラグ。 フラグの一覧については、 [Viewstatus](/windows/win32/api/ocidl/ne-ocidl-viewstatus)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
