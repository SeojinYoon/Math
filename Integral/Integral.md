
# Improper Integral

Improper integral은 일반적인 Riemann integral의 정의를 직접 적용할 수 없는 구간이나 함수에 대해 극한(Limit)을 이용하여 정의한 적분이다.

일반적인 정적분 $\int_{a}^{b} f(x)\,dx$은은 다음 두가지 조건이 필요하다.
1. 적분 구간 $[a, b]$가 유한한 닫힌 구간이어야 함
2. 피적분함수 $f(x)$가 해당 구간에서 유계(bounded, 무한대로 발산하지 않음)이어야 함.

이 둘 중 하나라도 만족하지 못할 때 이상적분을 사용한다.

## 이상적분의 두 가지 유형

1. Infinite Intervals

    적분 구간의 한쪽 또는 양쪽 끝이 무한대인 경우이다.

    정의 방식: $$\int_{a}^{\infty} f(x)\,dx = \lim_{t \to \infty} \int_{a}^{t} f(x)\,dx$$

    예시: $$\int_{1}^{\infty} \frac{1}{x^2}\,dx = \lim_{t \to \infty} \left[ -\frac{1}{x} \right]_{1}^{t} = \lim_{t \to \infty} \left( 1 - \frac{1}{t} \right) = 1$$

2. Unbounded / Discontinuous Integrands

    적분 구간은 유한하지만, 구간의 끝점이나 내부에서 함수가 $\pm\infty$로 발산하는 경우이다.

    - 정의 방식 (극한 사용, $x=a$에서 발산할 때):$$\int_{a}^{b} f(x)\,dx = \lim_{t \to a^+} \int_{t}^{b} f(x)\,dx$$
    - 예시 ($x=0$에서 $1/\sqrt{x} \to \infty$):$$\int_{0}^{1} \frac{1}{\sqrt{x}}\,dx = \lim_{t \to 0^+} \left[ 2\sqrt{x} \right]_{t}^{1} = \lim_{t \to 0^+} (2 - 2\sqrt{t}) = 2$$
