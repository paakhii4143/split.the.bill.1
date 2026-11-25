# split.the.bill.1
https://leetcode.com/project/split-the-bill/report/9mr0zt/

"""Split a restaurant bill. All amounts are integer cents."""


def apply_tip(subtotal_cents: int, percent: int) -> int:
    """Return the subtotal plus a percent% tip, rounded half up to the cent."""
    tip = (subtotal_cents * percent + 50) // 100
    return subtotal_cents + tip


def split_evenly(total_cents: int, people: int) -> list[int]:
    """Split the total into one share per person."""
    share, remainder = divmod(total_cents, people)
    return [share + (1 if i < remainder else 0) for i in range(people)]
