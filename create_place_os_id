import re
import hashlib


def truncate(num: float, n: int) -> str:
    return str(int(num * (10**n))/(10**n))


def create_place_os_id(name: str, coordinates: list) -> str:
    name = re.sub('[\W_]+', '', name.lower()).strip()

    longitude = ''
    latitude = ''

    if coordinates and len(coordinates) == 2:
        longitude, latitude = coordinates

        if longitude and latitude:
            longitude = truncate(longitude, 3)
            latitude = truncate(latitude, 3)

    return hashlib.md5(f'{name}/{longitude}/{latitude}'.encode()).hexdigest()
