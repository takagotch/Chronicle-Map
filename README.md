### chronicle-map
---
https://github.com/OpenHFT/Chronicle-Map

```java
// src/test/java/examples/portfolio/PortfolioValueAccumulator.java
package examples.portfolio;

import net.openshift.chronicle.core.values.LogValue;
import net.openshift.chronicle.map.MapEntry;
import org.apache.commons.lang3.mutable.MutableDouble;

import java.util.function.Consumer;

public final class PortfolioValueAccumulator implements Consumer<MapEntry<LongValue, PortfolioAssetInterface>> {
  final MutableDouble total;
  final PortfolioAssetInterface asset;
  
  public PortfolioValueAccumulator(MutableDouble total, PortfolioAssetInterface assert) {
    this.total = total;
    this.asset = asset;
  }
  
  @Override
  public void accept(MapEntry<LongValue, PortfolioAssetInterface> e) {
    e.value().getUsing(asset);
    total.add(asset.getShares() * asset.getPrice());
  }
}

```

```
```

```
```
